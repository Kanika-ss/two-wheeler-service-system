# Two-Wheeler Service System

A **Django-based web application** designed for managing two-wheeler service shop operations efficiently. This system automates job card creation, mechanic assignment, service tracking, and customer notifications.

---

## Project Overview
A two-wheeler service shop wants to regulate its **day-to-day service management**. Every incoming vehicle must be assigned a job card that includes essential details and service type. The system supports multiple service types, assigns mechanics based on workload, and sends automatic notifications upon job completion.

---

## Features
- **Job Card Management**
  - Create and store job cards with vehicle & service details.
  - Auto-assign mechanics based on **least workload**.
- **Mechanic Management**
  - Add new mechanics with login credentials.
  - View pending jobs and prioritize based on **expected delivery date**.
- **User Authentication**
  - Receptionist and mechanic login modules.
  - Credentials stored securely in CSV files.
- **Email Notifications**
  - Sends an **automatic email** to the vehicle owner after job completion using SMTP.
- **Persistent Data Handling**
  - Mechanic and job data stored using **Pickle files**.
  - Login details stored in **CSV files**.

---

## Technologies Used
- **Backend:** Python, Django
- **Design Patterns:**
  - Factory Pattern (Job Card creation)
  - Observer Pattern (Mechanic observes job updates)
  - Template Pattern (Job card creation process)
  - Iterator Pattern (CSV data reading)
- **Database:** CSV, Pickle files
- **Email Service:** SMTP protocol

---

## Modules Description
### 1. JobCard Module
- Base class `JobCard` and subclasses:
  - `MaintenanceJobCard`
  - `OilServiceJobCard`
  - `BrakeConditionJobCard`
- Stores details: Vehicle Reg. No., Owner Details, Engine No., Service Type, Expected Delivery Date.

### 2. JobCardFactory
- Implements **Factory Pattern** to create job cards dynamically.

### 3. Mechanic Module
- Handles **job assignment, completion, and priority ordering** based on delivery date.
- Uses **Observer Pattern** to update job status.

### 4. Authentication Module
- Receptionist and mechanic login functionality using **CSV-based credentials**.

### 5. Email Configuration
- Sends email notifications using **SMTP** after service completion.

