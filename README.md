# Fitness Coaching Platform - ER Diagram

## Overview

This project contains the Entity Relationship Diagram (ERD) for an online fitness coaching platform. The system is designed for influencers/trainers who provide structured coaching, consultations, subscriptions, and progress tracking for clients.

The platform supports:

* Online coaching plans
* Client subscriptions
* Consultation sessions
* Weekly check-ins
* Progress tracking
* Trainer feedback
* Payment tracking

---

## Business Requirements Covered

The database design supports:

* Trainers managing multiple clients
* Clients purchasing coaching plans
* Multiple clients enrolling in the same plan
* Subscription start and end tracking
* Session scheduling (consultation / coaching calls)
* Weekly check-in submissions
* Progress tracking (weight, measurements)
* Trainer notes and feedback
* Payment and subscription tracking

---

## Entities

### Users

Stores both trainers and clients

* user_id (PK)
* name
* email
* phone
* role
* created_at

---

### Trainers

Trainer-specific data

* trainer_id (PK)
* user_id (FK)
* specialization
* experience_years
* bio

---

### Clients

Client-specific data

* client_id (PK)
* user_id (FK)
* age
* gender
* height
* goal

---

### Plans

Coaching programs created by trainers

* plan_id (PK)
* trainer_id (FK)
* plan_name
* description
* duration_weeks
* price

---

### Subscriptions

Client plan purchases

* subscription_id (PK)
* client_id (FK)
* plan_id (FK)
* start_date
* end_date
* status

---

### Sessions

Consultation or coaching calls

* session_id (PK)
* trainer_id (FK)
* client_id (FK)
* session_type
* scheduled_at
* status
* notes

---

### Checkins

Weekly client submissions

* checkin_id (PK)
* client_id (FK)
* subscription_id (FK)
* weight
* body_fat
* notes
* submitted_at

---

### Progress

Body measurements and tracking

* progress_id (PK)
* client_id (FK)
* checkin_id (FK)
* chest
* waist
* hips
* trainer_notes

---

### Payments

Subscription payment tracking

* payment_id (PK)
* subscription_id (FK)
* amount
* payment_method
* payment_status
* paid_at

---

## Relationships

* One trainer can create many plans
* One client can subscribe to multiple plans
* One plan can have many clients
* One trainer can conduct multiple sessions
* Clients submit weekly check-ins
* Progress is tracked per check-in
* Payments linked to subscriptions

---

## Files

* `fitness-erd.txt` → ER diagram code
* `diagram.png` → exported diagram image
* `README.md` → documentation

---

## Assignment

Web Dev Cohort 2026
Database Design - Fitness Coaching Platform
