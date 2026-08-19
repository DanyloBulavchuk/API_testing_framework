# API_testing_framework
Automated REST API test suite for a booking management system using Postman, JavaScript assertions, and Newman CLI.

# RESTful Booker API Test Suite

Comprehensive automated and manual API testing suite built for the **Restful-Booker API** using **Postman** and **Newman CLI**.

## 📌 Project Overview
This repository contains a full end-to-end API test suite designed to validate functional requirements, data integrity, error handling, and response performance of a booking management system.

## 🛠️ Tech Stack & Tools
- **Tool:** Postman v10+
- **CLI Runner:** Newman
- **Format:** JSON / REST
- **Scripting:** JavaScript (Postman Sandbox)
- **CI-Ready:** Compatible with GitHub Actions / CLI execution

---

## 🧪 Test Coverage & Scenarios

### 1. Authentication & Security
- `POST /auth`: Generating Bearer/Auth tokens for secure admin endpoints.
- Auto-saving `token` to Environment variables via Pre-request/Tests scripts.

### 2. CRUD Operations
- `GET /booking`: Fetching list of all booking IDs with query filtering.
- `GET /booking/{id}`: Retrieving specific booking details and validating JSON Schema.
- `POST /booking`: Dynamic payload creation, validating `200 OK` / `201 Created` status and payload integrity.
- `PUT /booking/{id}`: Full update with valid authentication token and boundary data.
- `PATCH /booking/{id}`: Partial update testing specific fields (e.g., `additionalneeds`).
- `DELETE /booking/{id}`: Secure deletion and verifying idempotency (`405/404` on subsequent requests).

### 3. Edge Cases & Negative Testing
- Missing required fields in request payloads (`400 Bad Request`).
- Invalid date ranges (checkout before checkin).
- Unauthorized requests without token / with invalid token (`403 Forbidden`).
- Querying non-existent booking IDs (`404 Not Found`).

---

## 💻 Automated Assertions Implemented
Every request contains JavaScript test scripts validating:
- **Status Code Validation:** `pm.response.to.have.status(200)`
- **Response Time SLAs:** Response latency is within threshold (`< 800ms`)
- **JSON Schema & Data Types:** Ensuring correct property types (strings, booleans, integer IDs)
- **Business Logic Checks:** Response values strictly match the request body sent

---

## 🚀 How to Run Locally

### Option A: In Postman App
1. Clone this repository:
   ```bash
   git clone [https://github.com/](https://github.com/)<YOUR-USERNAME>/api-testing-framework-postman.git
