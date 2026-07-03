# Campus Complaint Management System

A full-stack web application for managing campus maintenance complaints, built using **Node.js**, **Express.js**, **MongoDB**, and a responsive **HTML, CSS, and JavaScript** frontend.

---

## Project Overview

The Campus Complaint Management System enables students and staff to report campus maintenance issues, monitor complaint status, and allows administrators and maintenance staff to efficiently assign, manage, and resolve complaints.

The backend exposes RESTful APIs for authentication, complaint management, reporting, and analytics.

---

## Features

### User Authentication

- User Registration
- Secure Login
- JWT Authentication
- Password Hashing using bcrypt
- Role-Based Authorization (User, Staff, Admin)

### Complaint Management

- Create maintenance complaints
- View complaint history
- Filter complaints by category and status
- Assign complaints to maintenance staff
- Update complaint status
- Delete complaints (Admin)

### Admin Dashboard

- Complaint Status Summary
- Category-wise Reports
- Staff Performance Reports
- Monthly Complaint Statistics

### Security

- JWT Authentication
- Password Encryption
- Input Validation
- Protected Routes
- Environment Variable Configuration

---

## Tech Stack

### Backend

- Node.js
- Express.js
- MongoDB
- Mongoose
- JWT
- bcryptjs
- CORS

### Frontend

- HTML5
- CSS3
- JavaScript

### Development Tools

- Git
- npm

---

## Project Structure

```
campus-complaint-management-system
│
├── backend/
│   ├── package.json
│   ├── server.js
│   └── src/
│       ├── middleware/
│       ├── models/
│       └── routes/
│
├── frontend/
│   └── campus_complaint_system.html
│
├── design/
│
├── .env.example
├── .gitignore
└── README.md
```

---

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/durga789/campus-complaint-management-system.git

cd campus-complaint-management-system
```

---

### 2. Install Backend Dependencies

```bash
cd backend

npm install
```

---

### 3. Configure Environment Variables

Create a `.env` file inside the `backend` folder.

Example:

```env
MONGO_URI=your_mongodb_connection_string

JWT_SECRET=your_secret_key
```

You can copy `.env.example` and update the values.

---

### 4. Start the Backend Server

```bash
npm start
```

or

```bash
npm run dev
```

---

### 5. Open the Frontend

Open

```
frontend/campus_complaint_system.html
```

in your browser

or

serve it using

```bash
npx http-server
```

---

## API Endpoints

### Authentication

| Method | Endpoint | Description |
|---------|----------|-------------|
| POST | `/api/auth/register` | Register a new user |
| POST | `/api/auth/login` | User login |

---

### Complaints

| Method | Endpoint | Description |
|---------|----------|-------------|
| POST | `/api/complaints` | Create complaint |
| GET | `/api/complaints` | Get complaints |
| GET | `/api/complaints/:id` | Get complaint by ID |
| GET | `/api/complaints/user/:userId` | User complaints |
| PUT | `/api/complaints/assign/:id` | Assign complaint |
| PUT | `/api/complaints/status/:id` | Update complaint status |
| DELETE | `/api/complaints/:id` | Delete complaint |

---

### Reports

| Method | Endpoint | Description |
|---------|----------|-------------|
| GET | `/api/reports/summary` | Complaint summary |
| GET | `/api/reports/categories` | Category report |
| GET | `/api/reports/staff/:id` | Staff report |
| GET | `/api/reports/monthly` | Monthly report |

---

## Example API Request

### Register

```bash
curl -X POST http://localhost:5000/api/auth/register \
-H "Content-Type: application/json" \
-d '{
"name":"John Doe",
"email":"john@example.com",
"password":"password123"
}'
```

---

### Login

```bash
curl -X POST http://localhost:5000/api/auth/login \
-H "Content-Type: application/json" \
-d '{
"email":"john@example.com",
"password":"password123"
}'
```

---

### Create Complaint

```bash
curl -X POST http://localhost:5000/api/complaints \
-H "Authorization: Bearer YOUR_JWT_TOKEN" \
-H "Content-Type: application/json" \
-d '{
"subject":"AC not working",
"description":"Room AC is not functioning",
"category":"Electrical",
"location":"Hostel A - Room 101",
"priority":"High"
}'
```

---

## Implementation Highlights

- JWT-based Authentication
- Role-Based Access Control
- Complaint Assignment Workflow
- Complaint Status Tracking
- Admin Reporting & Analytics
- MongoDB Integration using Mongoose
- Responsive User Interface
- RESTful API Design

---

## Security Features

- JWT Token Authentication
- Password Hashing using bcrypt
- Input Validation
- Protected API Routes
- Environment Variable Support

---

## Future Enhancements

- Email Notifications
- File/Image Upload for Complaints
- Real-Time Complaint Status Updates
- Mobile Responsive Improvements
- Deployment using Docker
- Unit & Integration Testing

---

## License

This project is intended for educational and portfolio purposes.
