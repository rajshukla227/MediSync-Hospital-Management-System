# 🏥 MediSync Database Architecture

This document describes the database architecture for the MediSync Hospital Management System.
## Database

- Database Name: medisync_db
- Database Type: PostgreSQL
- ORM: Prisma
- Language: TypeScript
## Design Principles

- Relational Database
- UUID as Primary Key
- Foreign Keys for Relationships
- Normalized Database Design
- Soft Delete Support
- Timestamp Tracking
## Main Entities

1. User
2. Role
3. Hospital
4. Department
5. Doctor
6. Patient
7. Appointment
8. Medical Record
9. Prescription
10. Medicine
11. Bill
12. Payment
13. Notification
14. Message
15. Audit Log
## Entity Description

### User
Stores login credentials and authentication details.

### Role
Defines system roles like Admin, Doctor, Nurse, and Patient.

### Hospital
Stores hospital information.

### Department
Stores hospital departments like Cardiology, Neurology, etc.

### Doctor
Stores doctor profiles and availability.

### Patient
Stores patient details and medical history.

### Appointment
Stores appointment booking information.

### Medical Record
Stores diagnosis, symptoms, reports, and treatment history.

### Prescription
Stores prescribed medicines and dosage instructions.

### Medicine
Stores medicine inventory and details.

### Bill
Stores invoices and billing information.

### Payment
Stores payment transactions and status.

### Notification
Stores email, SMS, and in-app notifications.

### Message
Stores chat messages between users.

### Audit Log
Stores system activity logs for security and tracking.
## Relationships Overview

- One Hospital has many Departments.
- One Department has many Doctors.
- One Doctor has many Appointments.
- One Patient has many Appointments.
- One Appointment has one Medical Record.
- One Medical Record has many Prescriptions.
- One Bill has one Payment.
- One User has one Role.