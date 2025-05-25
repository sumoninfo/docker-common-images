# 🐳 Docker Common Images

This project provides a Dockerized environment including:

- **MySQL 8.0**
- **Redis**
- **phpMyAdmin**
- Ready for integration with Drupal, Laravel, or other PHP apps

---

## 📥 Cloning the Repository

```bash
git clone https://github.com/sumoninfo/docker-common-images.git
cd docker-common-images
```

---

## 🧾 Environment Configuration

Create a `.env` file in the project root:

```env
MYSQL_ROOT_PASSWORD=root
MYSQL_DATABASE=app_db
MYSQL_USER=root
MYSQL_PASSWORD=root

DB_DATABASE=app_db
DB_USERNAME=root
DB_PASSWORD=root
DB_SERVER=mysql
```

---

## 🌐 Docker Network Setup

If not already created:

```bash
docker network create gp-shared-net
```

---

## 🚀 Starting the Services

```bash
docker compose up -d
```

---

## 🔎 Access Services

| Service     | URL                          |
|-------------|-------------------------------|
| MySQL       | `localhost:3309`             |
| Redis       | `localhost:6380`             |
| phpMyAdmin  | [http://localhost:8081](http://localhost:8081) |

---

## 🧹 Stopping and Cleanup

```bash
docker compose down
```

To remove volumes and unused networks:

```bash
docker compose down -v --remove-orphans
```

---

## 💡 Notes for Apple Silicon (M1/M2) Users

In `docker-compose.yml`, update phpMyAdmin section:

```yaml
image: arm64v8/phpmyadmin
platform: linux/arm64
```

---

## ✅ You're Ready!

Now you can start building and connecting your Drupal, Laravel, or custom PHP apps to this environment.