
# Event Management System

## Overview

This is a complete Event Management System built with PHP and MySQL. It provides an interface for admins to create and manage events, while users can browse, filter, and book events through a user-friendly frontend. The system includes payment integration, user authentication, and admin tools for managing bookings and customers.

---

## Features

### 🔐 User Authentication
- Secure login and registration.
- Authenticated users can book events.

### 📅 Event Management (Admin)
- Admin panel to create and manage events.
- Fields include:
  - Event Name
  - Description
  - Available Slots
  - Price
  - Time
  - Date
  - Venue
  - Category

### 🔎 Event Filtering (Frontend)
- AJAX-powered filters to search events by:
  - Category
  - Venue
  - Available Time/Date

### 💳 Booking & Payment
- Integrated payment gateway for event booking.
- Sends email confirmation upon successful booking.

### 🧑‍💼 Admin Controls
- Dashboard to:
  - View and manage all bookings.
  - Manage customer details.

---

## Technologies Used

- PHP (Core Backend)
- MySQL (Database)
- JavaScript & AJAX (Frontend Filtering)
- PHPMailer (Email Confirmation)
- Payment Gateway (Razorpay)
- HTML/CSS (Frontend UI)

---

## Prerequisites

Make sure you have the following installed:
- PHP 7.0 or higher
- MySQL
- XAMPP or similar (for local server)
- Composer (if using libraries like PHPMailer)

---

## Installation

### 1. Clone the Repository
```bash
git clone https://github.com/seshamarimuthu/event-management-system.git
```

### 2. Move Project to Server Directory
If using XAMPP, move it to the `htdocs` folder:
```
/xampp/htdocs/event_management_system
```

### 3. Create the Database
- Open **phpMyAdmin**
- Import the SQL file  `/events_db.sql/`

### 4. Configure Database Connection
Edit `db.php`:
```php
$host = "localhost";
$user = "root";
$pass = "";
$db = "events_db";

$conn = new mysqli($host, $user, $pass, $db);
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}
```

### 5. Configure PHPMailer (Optional)
if you change your domain email credentials, update the following in the /event-management-system/frontend/book.php file:
```php

$mailerEmail ='your_email@example.com'; 
$mailerPassword ='your_password';   
$mailerName = 'Your Name';

```

### 6. Configure Payment Gateway
Set your credentials in the respective payment config file ( `book.php`).
```php

$razorpayApiKey = 'YourrazorpayApiKey';  
$razorpaySecret = 'YourrazorpaySecret'; 

```

---

## Usage
run  http://localhost/event_management_system

- **Register** a new user:
  - If it’s the first registration, the user will be stored as `usertype = "admin"`.
  - All subsequent users will be stored as `usertype = "customer"`.

### 👤 User Side
- Visit the homepage to **browse events**.
- Use **AJAX-powered filters** to search by category, venue, date, or time.
- **Register/Login** to your account to enable booking.
- Choose an event and proceed to **book** it.
- Complete payment through the integrated gateway.
- Receive a **confirmation email** with all event details after successful booking.

### 🛠️ Admin Side
- Login as Admin via the **admin panel** (`/admin`).
- **Create and manage events**, including:
  - Name, description, slots, price, time/date, venue, and category.
- **View and manage bookings** made by users.
- **Access customer details** for each booking.

---

## License

This project is open-source and free to use.
