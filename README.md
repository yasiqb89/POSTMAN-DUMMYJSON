# 🧪 POSTMAN API Testing - DummyJSON Project

This project contains automated API tests for [DummyJSON](https://dummyjson.com/) — a public fake REST API for prototyping and learning.

All tests are written and organized using **Postman**, and executed via **Newman** (Postman's CLI), with CI support using **GitHub Actions**.

---

## 📁 Project Structure

```
POSTMAN-DUMMYJSON/
├── collections/
│   └── dummyjson-collection.json      # Main Postman collection (with folders/suites)
├── dummyjson-env.json                 # Postman environment file
├── reports/                           # Newman HTML reports (optional)
├── .github/
│   └── workflows/
│       └── api-tests.yml              # GitHub Actions workflow (if configured)
└── README.md                          # Project documentation
```

## ✅ Features Covered

| Feature Area     | Methods Covered                         |
|------------------|------------------------------------------|
| Auth Flow        | `POST /auth/login`, `GET /auth/me`, `POST /auth/logout` |
| Cart Flow        | `POST /carts/add`, `GET /carts/:id`, `DELETE /carts/:id` |
| Product Testing  | `GET /products`, `PUT`, `PATCH`, `Search` |
| Misc HTTP Methods| `HEAD`, `OPTIONS`, `DELETE`              |
| Status Validations | `200`, `201`, `204`, `400`, `401`, etc. |

All requests are grouped into logical **test suites** (folders) for structured testing and ease of automation.

---

## 🚀 How to Run Locally

### 1. Install Newman (if not installed)

```bash
npm install -g newman

# Run All Tests
newman run collections/dummyjson-collection.json -e dummyjson-env.json

# Run Specific 
newman run collections/dummyjson-collection.json \
  -e dummyjson-env.json \
  --folder "Cart Flow Suite"