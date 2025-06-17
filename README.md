# 🌟 Spring Boot + PostgreSQL CRUD Application

A simple demo application showcasing how to build a CRUD REST API using Spring Boot, Spring Data JPA, and PostgreSQL.

Built by following Ramesh Fadatare’s popular guide.

---

## 🚀 Features

- **CRUD operations** for a `User` (or `Employee`) entity
- Clean architecture using **Layered Design**:
  - Entity 📦
  - Repository 🔗
  - Service 🧠
  - Controller 🔁
- Automatic table creation using **Hibernate DDL**
- Uses PostgreSQL as the backend
- Running via **Spring Boot Maven Plugin**

---

## 📥 Download & Setup

```bash
git clone https://github.com/PavanSaxena/spring-boot-postgresql-crud
cd spring-boot-postgresql-crud
```

---

## 🛠 Prerequisites

- Java 17+ / 8+
- Maven 3.6+
- PostgreSQL server (local or remote)

Create a database (e.g., `mydb`) using:

```sql
CREATE DATABASE mydb;
```

---

## ⚙️ Configuration

Open `application.properties` (under `src/main/resources`) and configure:

```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/mydb
spring.datasource.username=YOUR_DB_USER
spring.datasource.password=YOUR_DB_PASS

spring.jpa.show-sql=true
spring.jpa.hibernate.ddl-auto=update
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.PostgreSQLDialect
```

🎯 Adjust `ddl-auto`:  
- `create` — recreate DB on every run  
- `update` — synchronize schema with entities

---

## ▶️ Run the Application

Use Maven plugin:

```bash
./mvnw spring-boot:run
```

Or run the main class:

```bash
mvn compile exec:java -Dexec.mainClass="com.example.SpringBootPostgresqlCrudApplication"
```

---

## 📦 REST Endpoints

| HTTP   | Endpoint           | Description             | Request Body    |
|--------|--------------------|-------------------------|------------------|
| GET    | `/api/users`       | List all users          | —                |
| GET    | `/api/users/{id}`  | Get single user by ID   | —                |
| POST   | `/api/users`       | Create new user         | JSON user object |
| PUT    | `/api/users/{id}`  | Update existing user    | JSON user object |
| DELETE | `/api/users/{id}`  | Delete user by ID       | —                |

---

## 🧱 Application Structure

```
src/
├─ main/
│  ├─ java/
│  │  ├─ controller/
│  │  │  └─ UserController.java
│  │  ├─ entity/
│  │  │  └─ User.java
│  │  ├─ repository/
│  │  │  └─ UserRepository.java
│  │  └─ service/
│  │     └─ UserService.java
│  └─ resources/
│     └─ application.properties
├─ test/
│  └─ java/
```

---

## ✅ Testing the API

You can test endpoints using:

- Postman
- `curl`, e.g.:

```bash
curl -X POST http://localhost:8080/api/users      -H "Content-Type: application/json"      -d '{"name":"Alice","email":"alice@example.com"}'
```

---

## ✨ Enhancements (To Do)

- Add **DTOs**
- Include **Exception Handling**
- Add **Validation**
- Add **Swagger/OpenAPI**
- Add **Tests**

---

## 📝 License

MIT or Apache 2.0