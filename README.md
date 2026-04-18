# Social Media Web App (Django)

A full‑stack social media web application built with **Django**. It provides a familiar social experience — user accounts and profiles, image posts, likes, following, search, user suggestions, and image download support.

---

## 🚀 Features

* 🔑 **User Authentication** — Signup, Login, Logout (Django auth)
* 👤 **Profile Management** — create & edit user profiles and account settings
* 📸 **Posts** — upload, edit, and delete image posts (with captions)
* ❤️ **Like / Unlike** posts
* 📰 **Feed** — aggregated posts from followed users and global feed
* 👥 **Follow / Unfollow** users
* 🔎 **Search** users and basic filtering (via `django-filter`)
* 🤖 **User Suggestions** — follow suggestions based on simple heuristics
* 📂 **Image Download** — allow users to download post images

---

## 🛠️ Tech Stack

* **Backend:** Django, Django ORM
* **Frontend:** Django templates (HTML, CSS, JavaScript), Bootstrap
* **Database:** SQLite (development), PostgreSQL (production)
* **Image handling:** Pillow
* **Filtering/searching:** django-filter
* **Optional:** Gunicorn + Nginx for production, Docker support

---

## 📁 Repository structure (example)

```
social_app/
├─ config/                  # Django project settings
├─ users/                   # User & profile app
├─ posts/                   # Posts, likes, feed app
├─ static/                  # CSS, JS, images
├─ media/                   # Uploaded images
├─ templates/               # Django templates
├─ requirements.txt
└─ README.md
```

---

## 🔧 Installation (development)

1. **Clone the repository**

```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
```

2. **Create & activate a virtual environment**

```bash
python -m venv venv
# macOS / Linux
source venv/bin/activate
# Windows
venv\Scripts\activate
```

3. **Install dependencies**

```bash
pip install -r requirements.txt
```

4. **Environment variables**

Create a `.env` file (not committed) with the essential variables:

```
SECRET_KEY=your-django-secret-key
DEBUG=True
DATABASE_URL=sqlite:///db.sqlite3
ALLOWED_HOSTS=localhost,127.0.0.1
```

For production with PostgreSQL (example):

```
DEBUG=False
DATABASE_URL=postgres://USER:PASSWORD@HOST:PORT/DBNAME
```

5. **Apply migrations & create superuser**

```bash
python manage.py migrate
python manage.py createsuperuser
```

6. **Run the dev server**

```bash
python manage.py runserver
```

Open [http://127.0.0.1:8000](http://127.0.0.1:8000)

---

### Docker (optional)

Provide a `Dockerfile` and `docker-compose.yml` for containerized deployments. Ensure media persistence via volumes.

---

## 🔐 Security & Best Practices

* Keep `SECRET_KEY` private and out of the repo
* Set `DEBUG=False` in production
* Use HTTPS and set `SECURE_SSL_REDIRECT`, `SESSION_COOKIE_SECURE`, `CSRF_COOKIE_SECURE`
* Validate and sanitize any user input
* Limit allowed upload types/sizes for images

---

## 🧪 Testing

Add tests under each app (`tests.py` or `tests/`) and run:

```bash
python manage.py test
```

Consider adding GitHub Actions/CI to run tests on push and PRs.

---

## ♻️ Image handling

Images are stored in the `media/` directory in development. The app uses `Pillow` to validate/process images. For production consider using cloud storage (AWS S3, DigitalOcean Spaces, etc.).

---

## 🧭 Useful management commands

* `python manage.py createsuperuser` — create admin account
* `python manage.py migrate` — apply migrations
* `python manage.py collectstatic` — collect static files

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch: `git checkout -b feat/your-feature`
3. Commit your changes and push: `git push origin feat/your-feature`
4. Open a pull request with a clear description of your changes

Please open issues for bugs or feature requests.

---

---

## 📦 Dependencies

See `requirements.txt`. Typical entries:

```
Django>=4.0
Pillow
django-filter
psycopg2-binary  # production (PostgreSQL)
gunicorn
python-dotenv
```

---

---

## 👋 Acknowledgements

Built with ❤️ using Django and the many open-source libraries that make web development fast and enjoyable.
