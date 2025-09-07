# Laravel + Blade Starter Kit

This is a Dockerised Laravel 12 + Blade starter kit focused for beginner to start explore in developing a web application. Powered with Docker setup to ease the development setup.

## Setup Guide

1. Install Docker Desktop (Windows / Mac) or Docker Engine (Linux).
2. Ensure docker and docker-compose commands work by running below command in terminal

```
docker --version
docker compose version
```

3. Git clone this repository

```
git clone https://github.com/nblkmal/larablade-starter-kit.git
```

4. Change directory to project directory `./larablade-starter-kit`, then run `docker-compose up -d`. You should see something like below

```
[+] Running 5/5
 ✔ Network larablade-starter-kit_laravel-network  Created                   0.0s 
 ✔ Container larablade-starter-kit-database-1     Started                   0.3s 
 ✔ Container larablade-starter-kit-app-1          Started                   0.3s 
 ✔ Container larablade-starter-kit-phpmyadmin-1   Started                   0.3s 
 ✔ Container larablade-starter-kit-web-1          Started                   0.4s 
 ```

 5. Open http://localhost:8080 in your browser. Your laravel web app should be accessible

---

# Student Registration System - Product Requirements Document (PRD)

## 1. Project Overview

### 1.1 Purpose
Develop a basic student registration system

### 1.2 Scope
**Phase 1 (MVP)**: Student Profile Management System
- Create and manage student profiles
- Basic student information storage and retrieval
- Simple registration workflow

**Future Phases**: Course enrollment, grades management, academic records, etc.

### 1.3 Target Users
- **Primary**: School administrators, registrars
- **Secondary**: Students (view-only access to their profiles)

## 2. Current System Analysis

### 2.1 Existing Infrastructure
- **Framework**: Laravel 12 with Blade templating
- **Database**: MySQL 8.0 (Dockerized)
- **Authentication**: Laravel Breeze (Login, Registration, Password Reset)
- **UI Framework**: CoreUI/AdminLTE inspired design
- **Frontend**: Blade + AlpineJS
- **Containerization**: Docker with nginx, PHP-FPM, MySQL, phpMyAdmin

### 2.2 Available Features
- User authentication system
- Dashboard with sidebar navigation
- Profile management (settings)
- Responsive design
- Database migrations and seeders

## 3. Student Profile Model Requirements

### 3.1 Core Student Information Fields

#### Personal Information
- **student_id** (string, unique) - Auto-generated student ID (e.g., STU-2024-001)
- **first_name** (string, required)
- **last_name** (string, required)
- **middle_name** (string, optional)
- **date_of_birth** (date, required)
- **gender** (enum: male, female, other, required)
- **nationality** (string, required)
- **phone_number** (string, optional)
- **email** (string, unique, required)
- **address** (text, required)
- **city** (string, required)
- **state_province** (string, required)
- **postal_code** (string, required)
- **country** (string, required)

#### Academic Information
- **enrollment_date** (date, required)
- **academic_year** (string, required) - e.g., "2024-2025"
- **program_of_study** (string, required) - e.g., "Computer Science", "Business Administration"
- **year_level** (enum: freshman, sophomore, junior, senior, graduate, required)
- **student_status** (enum: active, inactive, graduated, suspended, required)
- **gpa** (decimal, optional) - Current GPA

#### Emergency Contact
- **emergency_contact_name** (string, required)
- **emergency_contact_relationship** (string, required) - e.g., "Parent", "Guardian", "Sibling"
- **emergency_contact_phone** (string, required)
- **emergency_contact_email** (string, optional)

### 3.2 Data Validation Rules
- Email must be unique across all students
- Student ID must be auto-generated and unique
- Date of birth must be valid and reasonable (not future, not too old)
- Phone numbers must follow international format
- GPA must be between 0.0 and 4.0 (if provided)

## 4. Functional Requirements

### 4.1 Student Registration Workflow
1. **Registration Form**: Multi-step form for student information
2. **Data Validation**: Real-time validation of form fields
3. **Account Creation**: Automatic user account creation
4. **Profile Creation**: Student profile creation with provided information
5. **Confirmation**: Email confirmation and welcome message

### 4.2 Student Profile Management
1. **View Profile**: Display complete student information
2. **Edit Profile**: Allow updates to student information
3. **Search Students**: Search by name, student ID, email, or program
4. **List Students**: Paginated list with filtering options

### 4.3 Administrative Functions
1. **Student Dashboard**: Overview of student statistics
2. **Bulk Operations**: Import/export student data
3. **Reports**: Generate student reports (enrollment, demographics)

## 5. Technical Requirements

### 5.1 Database Design
```sql
-- Students table (extends users)
students:
- id (primary key)
- user_id (foreign key to users)
- student_id (unique string)
- first_name, last_name, middle_name
- date_of_birth, gender, nationality
- phone_number, email, address fields
- academic information fields
- emergency contact fields
- timestamps
```

**Document Version**: 1.0  
**Last Updated**: [Current Date]  
**Next Review**: [Date + 2 weeks]

