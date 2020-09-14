# Django Blog App

[![Python Version](https://img.shields.io/badge/python-3.7-brightgreen.svg)](https://python.org)
[![Django Version](https://img.shields.io/badge/django-2.1-brightgreen.svg)](https://djangoproject.com)

This is a very simple blog app using django web framework.

Features 
--

- User Registration
- Login And Logout System
- User Profile
- Update Profile
- Create, Update And Delete Posts
- Filtering Posts
- Password Reset

# How To Run Locally 

First, clone the repository to your local machine: 
```
$ git clone https://github.com/M0H3Y/django-blog && cd django-blgo
```

Install the requirements:
```
$ pip install -r requirements.txt
```

Run migrations: 
```
$ python3 manage.py makemigrations 
$ python3 manage.py migrate
```

Create A SuperUser:

```
$ python3 manage.py createsuperuser  
```

Run the Server : 

```
$ python3 manage.py runserver
```

Now, You can go to http://localhost:8000/ and you can login with the admin account in http://localhost:8000/admin/.

# Add Some Dummy Posts

First, Create Some User accounts. 

```python
$ python manage.py shell
>>> from blog.models import Post
>>> import json
>>> with open('posts.json') as f:
...     json_posts = json.load(f)
...
>>> for post in json_posts:
...     post = Post(title=post['title'], content=post['content'], author_id=post['user_id'])
...     post.save()
...
>>> exit()
```

