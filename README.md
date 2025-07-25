
---

# 🚗 Car Rental Management System (PHP + MySQL)

A web-based car rental platform built using procedural PHP, MySQL, Bootstrap, and jQuery. The system enables customers to book cars with drivers, employees to manage car and driver inventory, and includes complete rental return and billing workflows.

## 🔧 Tech Stack

* **Frontend:** HTML5, CSS3, Bootstrap, jQuery
* **Backend:** PHP (Procedural)
* **Database:** MySQL
* **Session Handling:** PHP Sessions

---

## 🧑‍💼 User Roles

### 1. **Customer**

* Register and log in
* Book available cars
* View active and past bookings
* Return rented cars
* See auto-generated invoice based on days or kilometers
* Get fined for late returns

### 2. **Employee (Client Panel)**

* Log in
* Add cars and drivers to inventory
* View all bookings
* Monitor vehicle availability and assignment
* Change car and driver availability status after return

---

## ✅ Features

### 🔐 Authentication

* **Customer login/registration**
* **Employee login**
* Session-based access control with personalized navigation

### 🚙 Car Booking Workflow

* Customers view available cars
* Booking includes:

  * Start and end date
  * Driver assignment
* Car availability updates after booking

### 👨‍✈️ Driver Assignment

* Every booking has an assigned driver
* Driver contact info shown in booking details
* Driver availability is tracked

### 📦 Return Workflow

* Customers return cars via `returncar.php`
* System fetches:

  * Car details
  * Booking duration
  * Charge type (`days` or `km`)
* If charged by km, the driver inputs distance
* Hidden inputs carry base fare and duration
* Form posts to `printbill.php`

### 🧾 Billing System

* Calculates:

  * Total amount = `fare * duration/distance`
  * Extra fine = ₹200/day for late returns
* Updates:

  * Car and driver availability (`yes`)
  * Return date
  * Total cost
* Displays formatted invoice with order number, fare details, fine (if any)

### 📊 Admin Panel (Client Panel)

* Add new cars via `entercar.php`
* Add new drivers via `enterdriver.php`
* View bookings via `clientview.php`

---

## 🗂️ Database Tables (Summary)

> Ensure MySQL database is connected via `connection.php`

### `customers`

* `customer_username`, `password`, `name`, etc.

### `cars`

* `car_id`, `car_name`, `car_nameplate`, `car_availability`

### `driver`

* `driver_id`, `driver_name`, `driver_phone`, `driver_availability`

### `rentedcars`

* `id`, `car_id`, `driver_id`, `customer_username`
* `rent_start_date`, `rent_end_date`, `car_return_date`
* `charge_type`, `fare`, `distance`, `no_of_days`
* `total_amount`, `return_status`

---

## ⚙️ Setup Instructions

1. Clone or download the repo
2. Set up a local server (e.g., XAMPP/LAMP)
3. Import SQL tables (if provided)
4. Update `connection.php` with your database credentials
5. Launch `index.php` in the browser

---

## 📝 Notes

* Built using procedural PHP for simplicity and accessibility.
* No third-party PHP frameworks used.
* Clean separation of user types and workflows.
* UI based on Bootstrap for responsiveness.

---


