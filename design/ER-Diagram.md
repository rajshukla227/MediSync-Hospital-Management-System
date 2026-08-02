# 🏥 MediSync ER Diagram

This document describes the Entity Relationship Diagram (ERD) for the MediSync Hospital Management System.
## Entities

- User
- Role
- Hospital
- Department
- Doctor
- Patient
- Appointment
- MedicalRecord
- Prescription
- Medicine
- Bill
- Payment
- Notification
- Message
- AuditLog
Role
 │
 │ 1
 │
 ▼
User
 │
 ├──────────────┐
 │              │
 ▼              ▼
Doctor       Patient
 │              │
 └──────┬───────┘
        │
        ▼
 Appointment
        │
        ▼
 MedicalRecord
        │
        ▼
 Prescription
        │
        ▼
 Medicine

Hospital
   │
   ▼
Department
   │
   ▼
Doctor

Patient
   │
   ▼
Bill
   │
   ▼
Payment

User
 ├────────► Notification
 ├────────► Message
 └────────► AuditLog
 ## Relationships

### Role → User
One Role can belong to many Users.

### Hospital → Department
One Hospital has many Departments.

### Department → Doctor
One Department has many Doctors.

### Doctor → Appointment
One Doctor can have many Appointments.

### Patient → Appointment
One Patient can book many Appointments.

### Appointment → MedicalRecord
One Appointment creates one Medical Record.

### MedicalRecord → Prescription
One Medical Record can have many Prescriptions.

### Prescription → Medicine
One Prescription can include many Medicines.

### Patient → Bill
One Patient can have many Bills.

### Bill → Payment
One Bill has one Payment.

### User → Notification
One User can receive many Notifications.

### User → Message
One User can send and receive many Messages.

### User → AuditLog
One User can generate many Audit Logs.
## Relationship Types

| Relationship | Type |
|--------------|------|
| Role → User | One-to-Many |
| Hospital → Department | One-to-Many |
| Department → Doctor | One-to-Many |
| Doctor → Appointment | One-to-Many |
| Patient → Appointment | One-to-Many |
| Appointment → MedicalRecord | One-to-One |
| MedicalRecord → Prescription | One-to-Many |
| Prescription → Medicine | Many-to-Many |
| Patient → Bill | One-to-Many |
| Bill → Payment | One-to-One |
| User → Notification | One-to-Many |
| User → Message | One-to-Many |
| User → AuditLog | One-to-Many |