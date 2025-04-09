# 🏥 Hospital Management System (Java + MySQL Console App)

This is a simple **console-based Hospital Management System** developed in Java using **JDBC for MySQL database connectivity**. It allows users to manage patients, view doctors, and book appointments.

---

## 📌 Features

- Add new patients
- View all registered patients
- View all doctors
- Book an appointment (with date and availability check)
- Prevent double-booking for doctors on the same date

---

## 🛠️ Technologies Used

- Java
- JDBC (Java Database Connectivity)
- MySQL
- Console I/O (Scanner)

---

## 📁 Project Structure


---

## 🧩 Database Schema

Create a MySQL database called `hospital` and run the following SQL commands to create required tables:

```sql
CREATE DATABASE hospital;

USE hospital;

CREATE TABLE patients (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    age INT,
    gender VARCHAR(10)
);

CREATE TABLE doctors (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    specialization VARCHAR(50)
);

CREATE TABLE appointments (
    id INT AUTO_INCREMENT PRIMARY KEY,
    patient_id INT,
    doctor_id INT,
    appointment_date DATE,
    FOREIGN KEY (patient_id) REFERENCES patients(id),
    FOREIGN KEY (doctor_id) REFERENCES doctors(id)
);

🚀 How to Run
Make sure MySQL is installed and running.

Create the database and tables as described above.

Open the project in any Java IDE (like IntelliJ or Eclipse).

Update the database credentials inside HospitalManagementSystem.java:

private static final String url = "jdbc:mysql://127.0.0.1:3306/hospital";
private static final String userName = "root";
private static final String password = "your_password";

 Sample Output
HOSPITAL MANAGEMENT SYSTEM
1: Add patient
2: View PATIENT
3: View DOCTOR
4: BOOK APPOINTMENT
5: EXIT
Enter your choice:
