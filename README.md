# 🏥 Hospital Management System (HMS)

## 📌 Overview

The Hospital Management System (HMS) is a web-based application designed to streamline hospital operations, including patient care, doctor management, appointment scheduling, billing, and user authentication. Built with modular architecture and following the MVC design pattern, HMS is compatible with both Java (Spring MVC) and .NET (ASP.NET Core MVC) frameworks.

## 🧩 Core Modules

- **Patient Management** – Handles patient records and medical history.
- **Doctor Management** – Manages doctor profiles and availability.
- **Appointment Scheduling** – Enables patients to book appointments.
- **Billing and Payments** – Manages billing and payment processing.
- **User Management** – Provides secure authentication and role-based access.

## 📐 Assumptions

- Local deployment using MySQL or SQL Server.
- Role-based authentication for secure access.
- ORM frameworks (Hibernate / Entity Framework) for database operations.
- No containerization during development.

## 🧱 Module-Level Design

### 1. Patient Management

**Controller**: `PatientController`
- `addPatient(patientData)`
- `updatePatient(patientId, patientData)`
- `getPatientDetails(patientId)`
- `deletePatient(patientId)`

**Service**: `PatientService`

**Entity**: `Patient`
- `patientId`
- `name`
- `dateOfBirth`
- `gender`
- `contactNumber`
- `address`
- `medicalHistory`

### 2. Doctor Management

**Controller**: `DoctorController`
- `addDoctor(doctorData)`
- `updateDoctor(doctorId, doctorData)`
- `getDoctorDetails(doctorId)`

**Service**: `DoctorService`

**Entity**: `Doctor`
- `doctorId`
- `name`
- `specialization`
- `contactNumber`
- `availabilitySchedule`

### 3. Appointment Scheduling

**Controller**: `AppointmentController`
- `scheduleAppointment(appointmentData)`
- `getAppointmentDetails(appointmentId)`
- `cancelAppointment(appointmentId)`

**Service**: `AppointmentService`

**Entity**: `Appointment`
- `appointmentId`
- `patientId`
- `doctorId`
- `appointmentDate`
- `timeSlot`
- `status` (ENUM: CONFIRMED, CANCELLED)

### 4. Billing and Payments

**Controller**: `BillingController`
- `generateBill(billData)`
- `getBillDetails(billId)`
- `processPayment(billId, paymentData)`

**Service**: `BillingService`

**Entity**: `Bill`
- `billId`
- `patientId`
- `totalAmount`
- `paymentStatus` (ENUM: PAID, UNPAID)
- `billDate`

### 5. User Management

**Controller**: `UserController`
- `registerUser(userData)`
- `loginUser(username, password)`
- `getUserProfile(userId)`

