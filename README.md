# Auditora - Event and Venue Management System

**Auditora** is a full-stack web application designed to streamline the booking and approval process for event venues across multiple college clubs. This system helps manage bookings for a variety of venues (auditoriums, classrooms) by enabling club members to request, track, and get approval for their events, while ensuring proper coordination between faculty, DSW (Director of Student Welfare), and the Facility Manager.

## Table of Contents
1. [Project Overview](#project-overview)
2. [Features](#features)
3. [User Roles and Permissions](#user-roles-and-permissions)
4. [Tech Stack](#tech-stack)
5. [Installation](#installation)
6. [Folder Structure](#folder-structure)
7. [API Endpoints](#api-endpoints)
8. [Frontend Components](#frontend-components)
9. [How to Contribute](#how-to-contribute)
10. [License](#license)

## Project Overview

Auditora is a centralized system designed for college clubs to request and manage venue bookings efficiently. With multiple clubs operating in the college, the system ensures smooth event scheduling without conflicts. The process is facilitated through a multi-level approval workflow involving club members, faculty coordinators, the Director of Student Welfare (DSW), and the Facility Manager.

The system provides a calendar interface where users can view available and booked slots for different venues. The booking status and approval process are transparently handled, ensuring compliance with college regulations.

## Features

### For Students (Users):
- View event calendar with upcoming club events in all venues
- Search for events by club, venue, or date
- Optionally, register for events if a registration system is implemented

### For Clubs:
- Submit a venue booking request (includes event details, preferred venue, date & time)
- Request approval from relevant faculty coordinators based on the club
- Track the status of their request (Pending, Approved, Rejected)
- Edit or cancel a pending booking request

### For Faculty Coordinators:
- View all submitted booking requests from their respective clubs
- Approve or reject the booking request
- Optionally, add comments on the request (e.g., "Requires further approval")

### For DSW (Director of Student Welfare):
- View and approve/reject all booking requests approved by faculty coordinators
- Ensure that event requests comply with college policies

### For Facility Manager:
- View the final list of approved bookings
- Assign a venue (Auditorium or Classroom) to the event
- Update venue status, ensuring the venue is marked as booked
- Update the calendar view to reflect venue updates in real-time

### Common Calendar:
- A **venue-wise calendar** shows bookings for each venue (Auditorium A, Classroom 101, etc.)
- Clicking on an event slot reveals the event details such as the club name, event title, and time

## User Roles and Permissions

| **Role** | **Permissions** |
|----------|-----------------|
| **Student (User)** | View event calendar |
| **Club (Organizer)** | Submit booking requests, track approval status |
| **Faculty Coordinator** | Approve/Reject requests from clubs |
| **DSW** | Final approval of event bookings |
| **Facility Manager** | Assign venues, update venue status |
| **Admin** | Full access to all roles and permissions |

## Tech Stack

- **Frontend:**  
  - React.js (for a dynamic user interface)
  - Tailwind CSS / ShadCN (for responsive and modern UI design)
  - FullCalendar.js (for displaying event calendars)

- **Backend:**  
  - Node.js (for API and backend logic)
  - Express.js (for routing and middleware)

- **Database:**  
  - MongoDB (for storing user data, booking requests, and event details)

- **Authentication:**  
  - JWT (for role-based authentication and session management)

- **Deployment:**  
  - Frontend: Vercel (for hosting the React frontend)
  - Backend: Render / Railway (for hosting the Node.js backend)
  - Database: MongoDB Atlas (for cloud database management)

## Installation

To run this project locally:

### 1. Clone the Repository:
```bash
git clone https://github.com/your-username/auditora.git
cd auditora
```

### 2. Setup Backend (Node.js + Express):
```bash
# Navigate to the server folder
cd server

# Install dependencies
npm install

# Create a .env file and add the necessary environment variables
# (e.g., MongoDB URI, JWT secret key)

# Start the backend server
npm start
```

### 3. Setup Frontend (React.js):
```bash
# Navigate to the client folder
cd client

# Install dependencies
npm install

# Start the frontend server
npm start
```

### 4. Open the App:
- Visit `http://localhost:3000` in your browser to access the web app.

## Folder Structure

```
Auditora/
├── client/               # React frontend
│   ├── public/           # Public assets (images, etc.)
│   ├── src/              # Source code for frontend
│   │   ├── components/   # Reusable components (Button, Card, etc.)
│   │   ├── pages/        # Pages like Home, Dashboard, etc.
│   │   ├── utils/        # Utility functions and helpers
│   │   └── App.jsx       # Main React App
│   └── package.json      # Frontend dependencies and scripts
├── server/               # Node.js backend
│   ├── controllers/      # Logic for handling API requests
│   ├── models/           # MongoDB models (User, Event, Booking, etc.)
│   ├── routes/           # API routes
│   ├── middleware/       # Middleware for auth, validation, etc.
│   ├── server.js         # Main backend server file
│   └── .env              # Environment variables
└── README.md             # Project documentation
```

## API Endpoints

- `POST /api/login` - User login (returns JWT token)
- `POST /api/register` - User registration
- `GET /api/events` - Fetch all events (for calendar view)
- `POST /api/booking` - Submit a booking request
- `GET /api/booking/:id` - Get booking details
- `PUT /api/booking/:id/approve` - Approve a booking request (Faculty Coordinator)
- `PUT /api/booking/:id/reject` - Reject a booking request (Faculty Coordinator)
- `PUT /api/booking/:id/finalize` - Finalize booking (DSW)
- `PUT /api/booking/:id/assign-venue` - Assign a venue to an event (Facility Manager)

## Frontend Components

- **Calendar View:** Uses `FullCalendar.js` to display venue-wise events
- **Booking Form:** Allows clubs to submit venue booking requests
- **Approval Dashboard:** Displays booking requests for Faculty Coordinators, DSW, and Facility Managers
- **User Authentication:** Login and role-based access management using JWT

## How to Contribute

1. Fork the repository
2. Create a feature branch (`git checkout -b feature-name`)
3. Make your changes and commit (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature-name`)
5. Create a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details.
