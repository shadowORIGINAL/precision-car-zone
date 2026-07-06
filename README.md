# Precision Car Zone

A web-based **car service center management system** built with PHP, MySQL, and JavaScript.

## Overview

Precision Car Zone is a service center platform that lets customers book vehicle services, browse the store, manage their profiles, and read the blog, while administrators and staff manage bookings, products, staff, and content from a dashboard. Payments are integrated via the Stripe API (test mode).

## Features

- Customer account registration, login, and profile management
- Online service booking and booking management
- Product store with cart and checkout (Stripe integration)
- Admin / Super Admin dashboards
- Staff management (add / edit staff)
- Blog with create / manage posts
- Responsive front-end (Bootstrap, jQuery, DataTables)

## Tech Stack

- **Back-end:** PHP (procedural), MySQL via `mysqli`
- **Front-end:** HTML, CSS, JavaScript, Bootstrap, jQuery, DataTables
- **Payments:** Stripe PHP SDK (`stripe/stripe-php`, installable via Composer)
- **Local server:** XAMPP (Apache + MySQL)

## Project Structure

- `db/` — database connection (`dbconn.php`)
- `css/`, `js/`, `assets/` — front-end styles and scripts
- `images/`, `Blogimages/`, `profileimages/`, `uploads/` — media assets
- `vendor/` — PHP dependencies (managed by Composer, not committed)

## Getting Started

### Prerequisites

- PHP 7.4+ (or compatible with the Stripe SDK)
- MySQL / MariaDB
- [Composer](https://getcomposer.org/)
- XAMPP (recommended for local development)

### Installation

1. Clone the repository into your web server root (e.g. XAMPP `htdocs`):

   ```bash
   git clone https://github.com/shadowORIGINAL/precision-car-zone.git
   ```

2. Install PHP dependencies:

   ```bash
   composer install
   ```

3. Create a MySQL database (e.g. `service_center`) and import your database schema / SQL dump.

4. Configure the database connection in `db/dbconn.php`:

   ```php
   $servername = "localhost";
   $username   = "root";
   $password   = "";
   $dbname     = "service_center";
   ```

5. Set the Stripe secret key via an environment variable (the key is no longer hardcoded in the code):

   ```bash
   set STRIPE_SECRET_KEY=sk_test_your_key_here
   ```

   The key is read in `configer.php` using `getenv('STRIPE_SECRET_KEY')`.

6. Start Apache and MySQL (XAMPP), then open the project in your browser:

   ```
   http://localhost/precision-car-zone/
   ```

## Environment Notes

- `configer.php` reads the Stripe secret key from the `STRIPE_SECRET_KEY` environment variable.
- The `vendor/` directory is excluded from version control. Run `composer install` after cloning.

## Credits

This project was developed as the **Final Project for the Higher Diploma in Computing and Software Engineering**, in collaboration with my colleagues from the **ICBT Kandy Campus**:

- **Kalana Wickramasinghe** (Me)
- **Avishka Sahan**
- **Thenuka Kulathunga**
- **Kalana Kavinda**
- **Dilum Kalhara**

## License

This repository is intended for educational / academic purposes.
