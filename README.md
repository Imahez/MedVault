# MedVault - Healthcare Management Platform

A comprehensive web-based platform for medical appointment scheduling, health record management, and patient-doctor interactions.

## 🏥 Overview

MedVault is a full-stack healthcare management system that connects patients with verified doctors, enabling seamless appointment booking, secure medical record storage, emergency consultations, and digital prescription management.

## ✨ Features

### For Patients
- **Appointment Booking** - Schedule appointments with verified doctors
- **Health Records** - Securely store and manage medical records
- **Digital Prescriptions** - View prescriptions from consultations
- **Emergency Requests** - Request urgent consultations
- **Doctor Reviews** - Rate and review doctors after appointments
- **Consent Management** - Control who can access your medical data

### For Doctors
- **Appointment Management** - View, approve, or reject appointments
- **Availability Slots** - Set and manage consultation schedules
- **Patient Records Access** - View patient records (with consent)
- **Digital Prescriptions** - Send prescriptions to patients
- **Emergency Handling** - Respond to emergency consultation requests
- **Qualification Upload** - Upload credentials for verification

### For Admins
- **Doctor Verification** - Review and verify doctor credentials
- **User Management** - Manage patients and doctors
- **Emergency Monitoring** - Track and manage emergency requests
- **Issue Resolution** - Handle reported issues
- **System Analytics** - View platform statistics

## 🛠️ Tech Stack

### Backend
- **Java 17** with **Spring Boot 3.5**
- **Spring Data JPA** for database operations
- **Spring Security** for authentication
- **MySQL** database
- **Maven** for dependency management

### Frontend
- **React 18** (via CDN with Babel)
- **Tailwind CSS** for styling
- **Lucide React** for icons
- **Vite** for development server

### Additional Services
- **Python Flask** chatbot service (MedBuddy)
- **JavaMail** for email notifications

## 📁 Project Structure

```
├── MedVault/
│   └── MedVal/                    # Spring Boot Backend
│       ├── src/main/java/com/medval/
│       │   ├── controller/        # REST API endpoints
│       │   ├── service/           # Business logic
│       │   ├── repository/        # Data access layer
│       │   ├── model/             # Entity classes
│       │   ├── dto/               # Data transfer objects
│       │   └── config/            # Configuration classes
│       ├── uploads/               # Medical records & prescriptions
│       └── pom.xml
│
├── MedVault-frontend/             # React Frontend
│   ├── index.html                 # Main application
│   ├── admin.html                 # Admin portal
│   └── public/                    # Static assets
│
├── chatbot/
│   └── chatbot_service/           # Python Flask Chatbot
│       ├── main.py
│       ├── chat_service.py
│       └── knowledge_base.json
│
└── uploads/
    └── qualifications/            # Doctor qualification documents
```

## 🚀 Getting Started

### Prerequisites
- Java 17 or higher
- Node.js 18 or higher
- MySQL 8.0
- Python 3.9+ (for chatbot)

### Database Setup

1. Create a MySQL database:
```sql
CREATE DATABASE medvault;
```

2. Update `application.properties` in `MedVault/MedVal/src/main/resources/`:
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/medvault
spring.datasource.username=your_username
spring.datasource.password=your_password
```

### Backend Setup

```bash
cd MedVault/MedVal
./mvnw spring-boot:run
```
Backend runs on `http://localhost:8080`

### Frontend Setup

```bash
cd MedVault-frontend
npm install
npm run dev
```
Frontend runs on `http://localhost:5173`

### Chatbot Setup (Optional)

```bash
cd chatbot/chatbot_service
pip install -r requirements.txt
python main.py
```
Chatbot runs on `http://localhost:5000`

## 📧 Email Configuration

Update email settings in `application.properties`:
```properties
spring.mail.host=smtp.gmail.com
spring.mail.port=587
spring.mail.username=your_email@gmail.com
spring.mail.password=your_app_password
```

## 🔗 API Endpoints

### Authentication
- `POST /api/auth/login` - User login
- `POST /api/auth/register/patient` - Patient registration
- `POST /api/auth/register/doctor` - Doctor registration

### Appointments
- `POST /api/appointments/book` - Book appointment
- `GET /api/appointments/patient/{id}` - Get patient appointments
- `GET /api/appointments/doctor/{id}` - Get doctor appointments
- `PUT /api/appointments/{id}/status` - Update appointment status

### Medical Records
- `POST /api/records/uploads/{patientId}` - Upload medical record
- `GET /api/records/patient/{patientId}` - Get patient records

### Emergency Requests
- `POST /api/emergency-requests/create` - Create emergency request
- `GET /api/emergency-requests/doctor/{id}` - Get doctor's emergency requests

## 📂 File Storage

| Type | Location |
|------|----------|
| Doctor Qualifications | `uploads/qualifications/` |
| Medical Records | `MedVault/MedVal/uploads/` |
| Prescriptions | `MedVault/MedVal/uploads/` |

## 🔐 User Roles

| Role | Access |
|------|--------|
| Patient | Book appointments, manage health records, view prescriptions |
| Doctor | Manage appointments, access patient records (with consent), send prescriptions |
| Admin | Verify doctors, manage users, monitor emergencies, resolve issues |

## 🤖 MedBuddy Chatbot

The integrated chatbot assists users with:
- Finding doctors by specialization
- Appointment booking guidance
- Medicine interaction checks
- Side effect information
- Symptom triage suggestions
- General FAQs

## 📱 Screenshots

The platform features:
- Modern gradient UI with purple theme
- Responsive design for all devices
- Dark mode support (Admin portal)
- Real-time notifications

## 🛡️ Security Features

- Password encryption with BCrypt
- Consent-based record access
- Role-based access control
- Secure file uploads with validation

## 📄 License

This project is developed for educational purposes.

## 👥 Contributors

<<<<<<< HEAD
- Development Team - MedVault Healthcare Solutions
=======
- Sreemaheshkumar
---

© 2025 MedVault Healthcare Solutions. All rights reserved.



To register an administrator using Postman, use the following request details. This target the backend API you have running on port 8080.

Request Details
Method: POST
URL: http://localhost:8080/api/auth/register/admin
Headers:
Content-Type: application/json
Raw Body (JSON)
You can copy and paste this into the Body tab in Postman, selecting the raw and JSON options:

json
{
  "email": "admin@medvault.com",
  "password": "admin123",
  "firstName": "Admin",
  "lastName": "User",
  "phone": "9876543210",
  "department": "IT Operations"
}

//Admin Login and Register

Register: If you haven't, register an admin using a POST request to http://localhost:8080/api/auth/register/admin.

Access: Go to http://localhost:5173/admin.html in your browser.

Login: Use the email admin@medvault.com and password securePassword123 (as per the README.md).
