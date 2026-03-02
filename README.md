🏥 Hospital Management System (Java-JDBC)

A robust, console-based Hospital Management System designed to streamline healthcare operations like patient registration, doctor management, and appointment scheduling. This project demonstrates the practical application of Object-Oriented Programming (OOPs) and Relational Database Management (RDBMS) using Java and MySQL.

🚀 Key Features
Patient Management: Allows users to register new patients and view a formatted list of all registered patients directly from the database.

Doctor Directory: Maintains a professional directory of doctors along with their specific specializations.

Smart Appointment Booking:

Validates whether the Patient ID and Doctor ID exist before proceeding.

Conflict Resolution: Features a logic-gate to check if a doctor is already booked for a specific date, preventing double-bookings.

Data Persistence: Uses JDBC to ensure all records (Patients, Doctors, Appointments) are stored permanently in MySQL.

Formatted CLI: Uses tabular formatting for a clean and professional user interface in the console.

🛠️ Tech Stack
Language: Java (JDK 17+)

Database: MySQL

Library: JDBC (Java Database Connectivity)

IDE: IntelliJ IDEA

🏗️ Project Architecture
The project follows a modular structure where each class has a specific responsibility:

HospitalManagementSystem.java: The main entry point that handles the user menu and core appointment booking logic.

Patient.java: Encapsulates all attributes and database operations related to patients.

Doctor.java: Manages doctor data and provides helper methods for verification.

🚦 Getting Started
1. Database Setup
Create a database named hospital and run the following SQL queries:

SQL
CREATE DATABASE hospital;
USE hospital;

CREATE TABLE patients (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    age INT NOT NULL,
    gender VARCHAR(10) NOT NULL
);

CREATE TABLE doctors (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    specialization VARCHAR(255) NOT NULL
);

CREATE TABLE appointments (
    id INT AUTO_INCREMENT PRIMARY KEY,
    patient_id INT NOT NULL,
    doctor_id INT NOT NULL,
    appointment_date DATE NOT NULL,
    FOREIGN KEY (patient_id) REFERENCES patients(id),
    FOREIGN KEY (doctor_id) REFERENCES doctors(id)
);
2. Configuration
Update the database credentials in HospitalManagementSystem.java:

Java
private static final String url = "jdbc:mysql://localhost:3306/hospital";
private static final String username = "root"; // Your MySQL Username
private static final String password = "your_password"; // Your MySQL Password
3. Execution
Add the mysql-connector-j JAR file to your project libraries.

Compile and run HospitalManagementSystem.java.

💡 Lessons Learned
During development, I encountered and resolved the Scanner buffer issue where nextInt() would skip subsequent nextLine() inputs. I also implemented PreparedStatement to ensure the application is secure against SQL Injection attacks.
