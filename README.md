# 🎬 Movie Service

A fully reactive RESTful backend service for managing movie information using **Spring WebFlux** and **Spring Data R2DBC** with **MySQL**.

This project demonstrates:
- Reactive programming with **Mono & Flux**
- Non-blocking database access using **R2DBC**
- Validation using **Jakarta Bean Validation**
- Global exception handling in WebFlux
- Clean layered architecture (Controller → Service → Repository)

---

## 🛠 Tech Stack
- **Java**
- **Spring Boot**
- **Spring WebFlux**
- **Spring Data R2DBC**
- **MySQL**
- **Lombok**
- **Jakarta Validation**

---

## 🗄 Database Schema

The schema is provided in `database.sql`.

### `movies` table

```sql
CREATE TABLE movies (
  id BIGINT AUTO_INCREMENT PRIMARY KEY,
  movie_name VARCHAR(255) NOT NULL,
  release_year VARCHAR(4) NOT NULL,
  cast_json JSON,
  release_date DATE
);
```
---

## 🧪 Dummy Data for Testing

You can insert the following records via Postman for testing.
```
{
  "movieName": "Inception",
  "releaseYear": "2010",
  "cast": "[\"Leonardo DiCaprio\", \"Joseph Gordon-Levitt\"]",
  "releaseDate": "2010-07-16"
}
```
---

## ✅ Validation Rules

`movieName` → Required, 2–100 characters

`releaseYear` → Must be a 4-digit year

`cast` → Required (stored as JSON string) 

`releaseDate` → Required
