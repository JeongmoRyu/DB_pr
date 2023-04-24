# DB M:N

html

```html
{% for article in articles %}
    <p>{{ article.title }}</p>
    <div>
      <form action="{% url 'articles:likes' article.pk %}" method="POST">
        {% csrf_token %}
        {% if comment in comments %}
          <button>좋아요 취소</button>
        {% else %}
          <button>좋아요</button>
        {% endif %}
      </form>
    </div>
    <p>좋아요 수: {{ comments|length }}</p>
  {% endfor %}
```

models.py

```python
class Article(models.Model):
    user = models.ForeignKey(settings.AUTH_USER_MODEL, on_delete=models.CASCADE)
    like_users = models.ManyToManyField(settings.AUTH_USER_MODEL, related_name="like_articles")
    title = models.CharField(max_length=10)
    content = models.TextField()
    created_at = models.DateTimeField(auto_now_add=True)
    updated_at = models.DateTimeField(auto_now=True)
```

views.py

```python
# articles/views.py

def likes(request, article_pk):
	article = Article.objects.get(pk=article_pk)
	if article.like_users.filter(pk=request.user.pk).exists():
		article.like_users.remove(request.user)
	else:
		article.like_users.add(request.user)

	return redirect('articles:index')
```