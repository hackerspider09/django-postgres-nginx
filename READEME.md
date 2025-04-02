
# 🐳 Django + PostgreSQL + Nginx with Docker

A fully Dockerized Django application using PostgreSQL as the database and Nginx as a reverse proxy. This setup ensures a production-ready deployment with Gunicorn handling WSGI requests.

## 🚀 Features
✅ **Django** - Web framework for backend logic  
✅ **PostgreSQL** - Robust database for storing application data  
✅ **Gunicorn** - WSGI server for running Django in production  
✅ **Nginx** - Reverse proxy to improve performance & serve static files  
✅ **Docker Compose** - Easily manage multi-container setup  
✅ **Environment Variables** - Configuration via `.env` file  

---

## 🏗 Project Structure

```
├── docker-compose.yaml   # Docker Compose configuration
├── Dockerfile            # Docker build file for Django
├── manage.py             # Django management script
├── nginx
│   └── nginx.conf        # Nginx configuration file
├── READE.md              # Documentation
├── requirements.txt      # Python dependencies
└── server                # Django project folder
    ├── asgi.py
    ├── __init__.py
    ├── settings.py
    ├── urls.py
    └── wsgi.py

```

---

## 🔧 Setup Instructions

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/hackerspider09/django-postgres-nginx
cd django-postgres-nginx
```

### 2️⃣ Create and Configure `.env`
```ini
# Django Settings
DJANGO_SECRET_KEY=your-secret-key
DJANGO_DEBUG=True
DJANGO_ALLOWED_HOSTS=localhost,127.0.0.1

# Database Configuration
POSTGRES_DB=postgres
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
POSTGRES_HOST=db
POSTGRES_PORT=5432
```

### 3️⃣ Build and Run Containers
```bash
docker-compose up --build -d
```


---

## 📌 Services Overview

| Service  | Container Name  | Description  | Port  |
|----------|----------------|-------------|------|
| Django  | `django_app` | Backend application  | 8000  |
| PostgreSQL | `postgres_db` | Database service  | 5432  |
| Nginx  | `nginx_server` | Reverse proxy  | 80  |

---


## 💡 Troubleshooting

❌ **Database connection issues?**  
✔️ Ensure PostgreSQL is running and `.env` variables are correct.

❌ **Static files not loading?**  
✔️ Run: `docker exec -it django_app python manage.py collectstatic --noinput`

❌ **Nginx not serving static files?**  
✔️ Check `nginx.conf` and restart the Nginx container:  
```bash
docker-compose restart nginx
```

---

## 🛠 Technologies Used
- Django 🐍
- PostgreSQL 🗄️
- Nginx 🌍
- Gunicorn 🦄
- Docker 🐳
- Docker Compose 🔧


