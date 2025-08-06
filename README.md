```markdown
# 📧 FastAPI + Celery + Redis Email Sender

This is a minimal project demonstrating how to send emails asynchronously using **FastAPI**, **Celery**, and **Redis** — containerized with **Docker**.

## 🚀 Features

- ✉️ Send email requests via FastAPI  
- ⚙️ Celery handles tasks asynchronously  
- 🧠 Redis as message broker  
- 🐳 Dockerized setup for easy deployment  

---

## 🗂️ Project Structure

```bash
.
├── docker-compose.yml     # Docker multi-service configuration
├── Dockerfile             # Web & worker Docker image definition
├── main.py                # FastAPI app with POST endpoint
├── tasks.py               # Celery task logic for sending email
└── worker.py              # Celery app instance
```

---

## 🧪 API Endpoint

| Method | Endpoint         | Description            |
|--------|------------------|------------------------|
| POST   | `/send-email/`   | Trigger email sending  |

### 🔧 Request Body Example

```json
{
  "email": "user@example.com",
  "subject": "Hello",
  "body": "This is a test email"
}
```

---

## 🐳 Running the Project

### 1️⃣ Build & Run

```bash
docker-compose up --build
```

### 2️⃣ Send a Test Email

```bash
curl -X POST http://localhost:8000/send-email/ \
  -H "Content-Type: application/json" \
  -d '{"email": "user@example.com", "subject": "Hi", "body": "Hello World!"}'
```

---

## 🧠 Notes

- The actual email sending is mocked with `print()` and `sleep(2)` in `tasks.py`.  
- In production, use real email providers like **SendGrid**, **Mailgun**, or SMTP.  
- Ensure port `8000` is not in use by other services.

---

## 📌 Requirements

If not using Docker, install dependencies manually:

```bash
pip install fastapi celery[redis] uvicorn
```

---

## 🧹 Clean Up

To stop the containers:

```bash
docker-compose down
```

---

## 📬 Credits

Made with ❤️ for asynchronous lovers.
```
