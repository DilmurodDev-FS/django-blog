# Django Blog Application

A beginner-friendly blog web application built with Python and Django.

## Features

- User registration, login, and logout
- Create, read, update, and delete blog posts
- Each post includes title, content, author, and created date
- SQLite database
- Bootstrap-styled templates
- Comment system under each post
- Django admin support

## Project Structure

```text
django_blog_app/
├── manage.py
├── requirements.txt
├── README.md
├── db.sqlite3                # Created after migrations
├── blogproject/
│   ├── __init__.py
│   └── blogproject/
│       ├── __init__.py
│       ├── settings.py
│       ├── urls.py
│       ├── asgi.py
│       └── wsgi.py
└── blog/
    ├── __init__.py
    ├── admin.py
    ├── apps.py
    ├── forms.py
    ├── models.py
    ├── urls.py
    ├── views.py
    ├── migrations/
    │   └── __init__.py
    └── templates/
        ├── blog/
        │   ├── base.html
        │   ├── post_list.html
        │   ├── post_detail.html
        │   ├── post_form.html
        │   └── post_confirm_delete.html
        └── registration/
            ├── login.html
            └── register.html
```

## How to Run

### 1) Create and activate a virtual environment

**Windows**
```bash
python -m venv venv
venv\Scripts\activate
```

**macOS / Linux**
```bash
python3 -m venv venv
source venv/bin/activate
```

### 2) Install dependencies
```bash
pip install -r requirements.txt
```

### 3) Create migrations and migrate
```bash
python manage.py makemigrations
python manage.py migrate
```

### 4) Create a superuser (optional, for admin panel)
```bash
python manage.py createsuperuser
```

### 5) Run the server
```bash
python manage.py runserver
```

### 6) Open in browser
- Blog home: http://127.0.0.1:8000/
- Admin panel: http://127.0.0.1:8000/admin/

## Important Parts Explained

### `models.py`
- `Post` stores blog posts.
- `Comment` stores comments linked to each post.

### `forms.py`
- `RegisterForm` creates a user signup form.
- `PostForm` handles creating/editing posts.
- `CommentForm` handles comments.

### `views.py`
- Class-based views manage list/detail/create/update/delete operations.
- `RegisterView` handles user registration.
- `add_comment` saves comments for logged-in users.

### `urls.py`
- Maps each page URL to the correct view.

## Notes
- This project is intended for learning and beginner practice.
- Before deploying to production, change `SECRET_KEY`, set `DEBUG=False`, and configure `ALLOWED_HOSTS`.
