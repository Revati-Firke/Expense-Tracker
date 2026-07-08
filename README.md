# Expense Tracker (Spring Boot)

Beginner-friendly expense tracker API based on the roadmap.sh project, but upgraded with modern backend concepts.

## Tech Stack (Latest + Practical)

- Java 17 (you can upgrade to Java 21 later)
- Spring Boot 3.5
- Spring Web + Validation
- Spring Data JPA (Hibernate)
- PostgreSQL 17
- Flyway (DB migrations)
- Spring Security (stateless setup, open endpoints for now)
- OpenAPI/Swagger UI
- JUnit 5 + Mockito

## Implemented Features (Step by Step)

### Feature 1: Expense CRUD ✅

- Add expense
- Update expense
- Delete expense
- List expenses

### Feature 2: Summary ✅

- Total monthly expense
- Monthly summary by category
- Top spending category

### Feature 3: Budget Tracking ✅

- Set budget for a month
- Check budget status
- Warning when budget exceeded

### Feature 4: Export ✅

- Export expenses to CSV for a selected month

### Feature 5 (Unique): No-Spend Streak ✅

- Summary includes no-spend streak days (simple motivational feature)

### Feature 6: Recurring Marker ✅

- You can mark an expense as recurring (monthly subscriptions etc.)

---

## Roadmap (Next Features You Can Build)

1. User authentication with JWT (multi-user support)
2. Category management in DB (instead of enum)
3. Recurring expense auto-generation scheduler
4. Alerts (email/telegram) when nearing budget
5. Dashboard frontend (React/Angular)
6. AI insights (spending suggestions)

---

## Project Structure (Clean and Simple)

- `expense` module: expense domain, API, service, repository
- `budget` module: monthly budget API + service
- `shared` module: global exception handling and common responses
- `config` module: security setup

---

## Quick Start

### 1) Start PostgreSQL

```bash
docker compose up -d
```

### 2) Run the app

```bash
./mvnw spring-boot:run
```

### 3) Open API docs

- Swagger UI: http://localhost:8080/swagger-ui.html
- OpenAPI JSON: http://localhost:8080/api-docs

---

## Main API Endpoints

### Expenses

- `POST /api/v1/expenses`
- `PUT /api/v1/expenses/{id}`
- `DELETE /api/v1/expenses/{id}`
- `GET /api/v1/expenses?month=7&category=FOOD`
- `GET /api/v1/expenses/summary?month=7`
- `GET /api/v1/expenses/export/csv?month=7`

### Budgets

- `POST /api/v1/budgets`
- `GET /api/v1/budgets/{year}/{month}`

---

## Example Requests

### Create Expense

```json
{
  "description": "Lunch",
  "amount": 12.5,
  "category": "FOOD",
  "expenseDate": "2026-07-06",
  "recurring": false,
  "note": "Office cafeteria"
}
```

### Set Budget

```json
{
  "year": 2026,
  "month": 7,
  "limitAmount": 20000
}
```

---

## Learning Notes (For You)

- `Entity` = table mapping
- `Repository` = DB access layer
- `Service` = business logic
- `Controller` = HTTP endpoints
- `DTO` = request/response models
- `Flyway` = versioned DB schema changes

If you want, next I can implement **Feature 7: JWT login/register** in the same clean style.
