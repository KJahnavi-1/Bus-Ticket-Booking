# Bus Ticket Booking System (C Language)

## Overview

This project implements a simple console-based Bus Ticket Booking System using the C programming language. It simulates core functionalities required for managing bus reservations, including user login, booking tickets, canceling tickets, and checking bus availability status.

The system is designed for ease of use in a command-line interface, making it a foundational example for understanding data structures, function calls, and basic user interaction in C.

## Features

* **User Login:** Simple authentication system with a predefined username and password.
* **Book a Ticket:** Users can select a bus by its number and book a specified number of seats, with checks for seat availability.
* **Cancel a Ticket:** Users can cancel previously booked seats for a specific bus.
* **Check Bus Status:** Display detailed information for a selected bus, including its route, total seats, available seats, and fare.
* **Persistent Session (within runtime):** Allows multiple transactions until the user logs out or exits the program.

## Algorithm

The system operates based on the following algorithmic steps:

1.  **Start:** Initialize the program.
2.  **Initialize Bus & User Data:**
    * Define a `Bus` structure containing: `busNumber`, `source`, `destination`, `totalSeats`, `availableSeats`, `fare`.
    * Define a `User` structure containing: `username`, `password`.
    * Pre-populate arrays with sample `Bus` and `User` data.
3.  **Display Main Menu:**
    * Present options: `1. LOGIN`, `2. EXIT`.
    * Prompt the user for their choice.
4.  **Login Process (if choice is 1):**
    * Ask for username and password.
    * Authenticate against the predefined user data.
    * If successful, proceed to the User Menu. If failed, display an error and return to the Main Menu.
5.  **User Menu (after successful login):**
    * Present options: `1. Book a Ticket`, `2. Cancel a Ticket`, `3. Check Bus Status`, `4. Logout`.
    * Prompt the user for their choice.
6.  **Book a Ticket (Option 1):**
    * Display available bus details (Bus Number, Source, Destination, Total Seats, Available Seats, Fare).
    * Prompt the user to enter a bus number.
    * If the bus is found:
        * Prompt for the number of seats to book.
        * Check if sufficient `availableSeats` exist.
        * If yes, decrement `availableSeats`, confirm booking.
        * If no, inform "Insufficient seats".
    * If the bus is not found, inform the user.
7.  **Cancel a Ticket (Option 2):**
    * Prompt the user to enter a bus number.
    * If the bus is found:
        * Prompt for the number of seats to cancel.
        * Check if the number of seats to cancel does not exceed the already booked seats (`totalSeats - availableSeats`).
        * If yes, increment `availableSeats`, confirm cancellation.
        * If no, inform "Error: cannot cancel more seats than booked."
    * If the bus is not found, inform the user.
8.  **Check Bus Status (Option 3):**
    * Prompt the user to enter a bus number.
    * If the bus is found, display all its details (`busNumber`, `source`, `destination`, `totalSeats`, `availableSeats`, `fare`).
    * If the bus is not found, inform the user.
9.  **Logout (Option 4):**
    * Reset `loggedInUserId` to -1, returning the user to the Main Menu.
10. **Exit (from Main Menu, Option 2):**
    * Terminate the program.
