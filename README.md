---

# 🎓 College Directory Application

A role-based **College Directory Application** built using **Spring Boot**, **MySQL**, and a simple **HTML/CSS/JavaScript** frontend. The application enables interaction between students, faculty members, and administrators within a college environment by managing academic profiles and records.

---

## 🚀 Features

### 👨‍🎓 Student Features

* View personal profile (photo, contact, academic details)
* Search for other students by name, department, or year
* View and contact assigned faculty advisors

### 👩‍🏫 Faculty Features

* View class lists of assigned students
* Update personal details like office hours and contact info

### 🛠 Administrator Features

* Perform CRUD operations on student and faculty records
* View a dashboard with graphs (e.g., enrollment trends, faculty workloads)

---

## ⚙️ Tech Stack

| Layer    | Technology                     |
| -------- | ------------------------------ |
| Frontend | HTML, CSS, JavaScript          |
| Backend  | Java (Spring Boot via STS)     |
| Database | MySQL                          |
| Tools    | Spring Tool Suite (STS), Maven |

---

## 🧱 Data Model Overview

### 🔹 Core Entities

* **User**: Common base for Student, Faculty, Admin roles
* **StudentProfile**, **FacultyProfile**, **AdministratorProfile**
* **Course**, **Enrollment**, **Department**

### 🔹 Key Relationships

* `User ↔ Profile`: One-to-One
* `Faculty → Courses`: One-to-Many
* `Students ↔ Courses`: Many-to-Many via Enrollment
* `Department → Profiles/Courses`: One-to-Many

---

## 🧪 MySQL Schema Sample

```sql
CREATE TABLE User (
  id INT AUTO_INCREMENT PRIMARY KEY,
  username VARCHAR(50) UNIQUE NOT NULL,
  password VARCHAR(255) NOT NULL,
  role ENUM('STUDENT', 'FACULTY_MEMBER', 'ADMINISTRATOR') NOT NULL,
  name VARCHAR(100),
  email VARCHAR(100) UNIQUE,
  phone VARCHAR(15)
);
```

Additional tables include: `StudentProfile`, `FacultyProfile`, `AdministratorProfile`, `Course`, `Enrollment`, `Department`.

---

## 🧰 Running the Application

### Prerequisites

* Java 17+
* Spring Tool Suite (STS)
* MySQL
* Maven

### Steps

1. **Clone the repository**:

   ```bash
   git clone https://github.com/RajivP18/college_directory_application_SpringBoot.git
   ```

2. **Open the project in STS**:

   * File → Import → Maven → Existing Maven Project
   * Configure database credentials in `application.properties`

3. **Run the project**:

   * Right-click on the project → Run As → Spring Boot App
   * Access the app via `http://localhost:8080`

---

## 📊 Admin Dashboard

* Includes charts and graphs for visualizing:

  * Enrollment data
  * Faculty course loads
* Data is aggregated and fetched from the backend

---

## 🤝 Contributions

If you'd like to contribute:

1. Fork the repo
2. Create a branch (`feature/your-feature`)
3. Commit your changes
4. Open a pull request

---
