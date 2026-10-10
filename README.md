# Aarogya | Ambulance Booking Website

A locally runnable PHP and MySQL website for browsing transport listings and submitting booking requests. The interface is branded for Aarogya ambulance services; parts of the underlying application and database still use car-rental terminology.

## What’s included

- Public pages for browsing listings, filtering by brand and fuel type, and viewing listing details.
- User registration and login, profile pages, and booking history.
- Booking request submission and an administration area for managing listings and reviewing bookings.
- A MySQL schema and sample records in [`carrental.sql`](./carrental.sql).
- Static frontend assets in `assets/` and administration pages and uploaded images in `admin/`.

This is a student project/demo, not a production dispatch system. In particular, the existing data model is vehicle-rental-oriented and should not be treated as supporting emergency dispatch or real-time ambulance availability.

## Run locally with XAMPP

1. Install XAMPP and copy this project folder into `C:\xampp\htdocs\`.
2. Open the XAMPP Control Panel and start **Apache** and **MySQL**.
3. Visit [phpMyAdmin](http://localhost/phpmyadmin/).
4. Create a database named `carrental`.
5. Select that database, open **Import**, choose the project’s root-level `carrental.sql`, and start the import.
6. Open the application at [http://localhost/online_ambulance_booking_service-master/](http://localhost/online_ambulance_booking_service-master/).
7. The administration sign-in page is at [http://localhost/online_ambulance_booking_service-master/admin/](http://localhost/online_ambulance_booking_service-master/admin/).

The connection settings are in [`includes/config.php`](./includes/config.php) and [`admin/includes/config.php`](./admin/includes/config.php). By default, both expect MySQL on `localhost`, database `carrental`, username `root`, and an empty password, as commonly configured by a fresh XAMPP installation. If your MySQL credentials differ, update both files.

If Apache is configured to use another port, include that port in the browser address—for example, `http://localhost:8080/online_ambulance_booking_service-master/`.

## Project layout

| Path | Purpose |
| --- | --- |
| `index.php` | Home page |
| `car-listing.php` | Browse available listings |
| `search-carresult.php` | Filtered listing results |
| `vehical-details.php` | Listing details and booking form |
| `my-booking.php` | Signed-in user’s bookings |
| `admin/` | Administration pages |
| `includes/` | Shared configuration and user-facing components |
| `carrental.sql` | Database tables and sample data |

## Notes for development

- The imported database is named `carrental`, and the schema retains names such as `tblvehicles`, `tblbrands`, and `tblbooking`.
- The SQL file and image directory need to stay in sync: vehicle image filenames are stored in the database and served from `admin/img/vehicleimages/`.
- Use only test data on a local installation. Before exposing the application to other users, review password storage, access control, file uploads, input validation, and deployment configuration.
- Do not expose a production database password in a publicly served PHP configuration file.

## Background and credits

This codebase is based on the Aarogya project shared at the [original project page](https://meharima.github.io/online_ambulance_booking_service/). The original author’s demo is available on [YouTube](https://youtu.be/156Att0_Ndk).
