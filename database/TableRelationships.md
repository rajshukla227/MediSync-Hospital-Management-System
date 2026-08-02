# 🏥 MediSync Table Relationships

This document defines all relationships between database tables.

## 1. Role → User

Relationship:
One Role → Many Users

Foreign Key:
User.roleId → Role.id

Example:

Doctor
 ├── Raj
 ├── Aman
 └── Rohit

 ## 2. Hospital → Department

Relationship:
One Hospital → Many Departments

Foreign Key:
Department.hospitalId → Hospital.id

Example:

City Hospital
 ├── Cardiology
 ├── Neurology
 ├── Orthopedics
 └── Emergency


 ## 3. Department → Doctor

Relationship:
One Department → Many Doctors

Foreign Key:
Doctor.departmentId → Department.id

Example:

Cardiology
 ├── Dr. Sharma
 ├── Dr. Singh
 └── Dr. Khan

## 4. User → Doctor

Relationship:
One User → One Doctor

Foreign Key:
Doctor.userId → User.id

## 5. User → Patient

Relationship:
One User → One Patient

Foreign Key:
Patient.userId → User.id

## 6. Patient → Appointment

Relationship:
One Patient → Many Appointments

Foreign Key:
Appointment.patientId → Patient.id

## 7. Doctor → Appointment

Relationship:
One Doctor → Many Appointments

Foreign Key:
Appointment.doctorId → Doctor.id

## 8. Appointment → MedicalRecord

Relationship:
One Appointment → One Medical Record

Foreign Key:
MedicalRecord.appointmentId → Appointment.id

## 9. MedicalRecord → Prescription

Relationship:
One Medical Record → Many Prescriptions

Foreign Key:
Prescription.medicalRecordId → MedicalRecord.id


## 10. Prescription ↔ Medicine

Relationship:
Many Prescriptions ↔ Many Medicines

Implemented Using:
PrescriptionMedicine (Junction Table)

Foreign Keys:

PrescriptionMedicine.prescriptionId → Prescription.id

PrescriptionMedicine.medicineId → Medicine.id

## 11. Patient → Bill

Relationship:
One Patient → Many Bills

Foreign Key:
Bill.patientId → Patient.id


## 12. Bill → Payment

Relationship:
One Bill → One Payment

Foreign Key:
Payment.billId → Bill.id

## 13. User → Notification

Relationship:
One User → Many Notifications

Foreign Key:
Notification.userId → User.id

## 14. User → AuditLog

Relationship:
One User → Many Audit Logs

Foreign Key:
AuditLog.userId → User.id


| Parent Table  | Child Table   | Relationship |
| ------------- | ------------- | ------------ |
| Role          | User          | One-to-Many  |
| Hospital      | Department    | One-to-Many  |
| Department    | Doctor        | One-to-Many  |
| User          | Doctor        | One-to-One   |
| User          | Patient       | One-to-One   |
| Patient       | Appointment   | One-to-Many  |
| Doctor        | Appointment   | One-to-Many  |
| Appointment   | MedicalRecord | One-to-One   |
| MedicalRecord | Prescription  | One-to-Many  |
| Prescription  | Medicine      | Many-to-Many |
| Patient       | Bill          | One-to-Many  |
| Bill          | Payment       | One-to-One   |
| User          | Notification  | One-to-Many  |
| User          | AuditLog      | One-to-Many  |
