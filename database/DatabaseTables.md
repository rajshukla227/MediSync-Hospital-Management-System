# 🏥 MediSync Database Tables

This document contains all database tables, columns, data types, keys, and constraints.

## Table: Role

| Column | Type | Constraints |
|---------|------|-------------|
| id | UUID | Primary Key |
| name | String | Unique |
| description | String | Optional |
| createdAt | DateTime | Default Now |
| updatedAt | DateTime | Auto Update |

## Table: User

| Column | Type | Constraints |
|---------|------|-------------|
| id | UUID | Primary Key |
| fullName | String | Required |
| email | String | Unique |
| password | String | Required |
| phone | String | Unique |
| profileImage | String | Optional |
| isVerified | Boolean | Default False |
| status | String | Active/Inactive |
| roleId | UUID | Foreign Key |
| createdAt | DateTime | Default Now |
| updatedAt | DateTime | Auto Update |
## Table: Hospital

| Column | Type |
|---------|------|
| id | UUID |
| name | String |
| address | String |
| city | String |
| state | String |
| country | String |
| phone | String |
| email | String |
| website | String |
| createdAt | DateTime |
| updatedAt | DateTime |

## Table: Department

| Column | Type |
|---------|------|
| id | UUID |
| hospitalId | UUID |
| name | String |
| description | String |
| createdAt | DateTime |


## Table: Doctor

| Column | Type |
|---------|------|
| id | UUID |
| userId | UUID |
| departmentId | UUID |
| specialization | String |
| qualification | String |
| experience | Int |
| consultationFee | Decimal |
| availability | Boolean |
| createdAt | DateTime |
| updatedAt | DateTime |

## Table: Patient

| Column | Type |
|---------|------|
| id | UUID |
| userId | UUID |
| bloodGroup | String |
| gender | String |
| dateOfBirth | Date |
| emergencyContact | String |
| allergies | String |
| insuranceNumber | String |
| createdAt | DateTime |
| updatedAt | DateTime |

## Table: Appointment

| Column | Type |
|---------|------|
| id | UUID |
| patientId | UUID |
| doctorId | UUID |
| appointmentDate | DateTime |
| status | String |
| reason | String |
| notes | String |
| createdAt | DateTime |
| updatedAt | DateTime |

## Table: MedicalRecord

| Column | Type |
|---------|------|
| id | UUID |
| appointmentId | UUID |
| diagnosis | String |
| symptoms | String |
| treatment | String |
| report | String |
| createdAt | DateTime |
| updatedAt | DateTime |

## Table: Prescription

| Column | Type |
|---------|------|
| id | UUID |
| medicalRecordId | UUID |
| medicineName | String |
| dosage | String |
| frequency | String |
| duration | String |
| instructions | String |
| createdAt | DateTime |

## Table: Bill

| Column | Type |
|---------|------|
| id | UUID |
| patientId | UUID |
| totalAmount | Decimal |
| discount | Decimal |
| tax | Decimal |
| finalAmount | Decimal |
| status | String |
| createdAt | DateTime |


## Table: Payment

| Column | Type |
|---------|------|
| id | UUID |
| billId | UUID |
| paymentMethod | String |
| transactionId | String |
| amount | Decimal |
| paymentStatus | String |
| paidAt | DateTime |

## Table: Notification

| Column | Type |
|---------|------|
| id | UUID |
| userId | UUID |
| title | String |
| message | String |
| isRead | Boolean |
| createdAt | DateTime |

## Table: AuditLog

| Column | Type |
|---------|------|
| id | UUID |
| userId | UUID |
| action | String |
| entity | String |
| entityId | UUID |
| createdAt | DateTime |