
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
- Payment Gateway (e.g., Stripe/PayPal)
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
/xampp/htdocs/event-management-system
```

### 3. Create the Database
- Open **phpMyAdmin**
- Create a new database: `event_management`
- Import the SQL file located in `/sql/` folder

### 4. Configure Database Connection
Edit `config.php`:
```php
$servername = "localhost";
$username = "root";
$password = "";
$database = "event_management";
$conn = new mysqli($servername, $username, $password, $database);
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}
```

### 5. Configure PHPMailer (Optional)
In `mailer_config.php` or wherever used:
```php
$mail->Username = 'your_email@example.com';
$mail->Password = 'your_password';
$mail->setFrom('your_email@example.com', 'Your Name');
```

### 6. Configure Payment Gateway
Set your credentials in the respective payment config file (e.g., `stripe_config.php` or `paypal_config.php`).

---

## Usage

- **Register/Login** as a user.
- **Browse & Filter Events** on the home page.
- **Book an Event** → Redirects to payment → Email confirmation sent.
- **Admin Panel**: Login to `/admin` to create, edit, and manage events/bookings.

---

## License

This project is open-source and free to use.
