
# Bus Ticket Booking System

## Table of Contents

1. [Setting up Backend (Spring Boot)](#setting-up-backend-spring-boot)
2. [Setting Up Frontend (HTML, CSS, and JS or Thymeleaf Template)](#setting-up-frontend-html-css-and-js-or-thymeleaf-template)
3. [User Registration and Authentication](#user-registration-and-authentication)
4. [Bus Ticket Booking](#bus-ticket-booking)
5. [User Profile and Booking History](#user-profile-and-booking-history)
6. [API Endpoints](#api-endpoints)
7. [Testing and Quality Assurance](#testing-and-quality-assurance)

## Setting up Backend (Spring Boot)

A. Create a new Spring Boot project.

B. Define entities (e.g., Bus, Booking, Passenger) and set up the necessary data models.

C. Implement RESTful APIs using Spring Boot's controllers to handle bus booking requests, user authentication, and data retrieval from a database.

D. Set up a database (e.g., MySQL, MongoDB) to store bus schedules, booking information, and user data.

## Setting Up Frontend (HTML, CSS, and JS or Thymeleaf Template)

A. Design the user interface (UI) for the app using HTML, JS, and CSS. Develop responsive web pages for listing available bus routes, booking forms, and user profiles.

B. Utilize CSS frameworks (e.g., Bootstrap) for styling to enhance the user experience.

## User Registration and Authentication

1. **User Registration:**

   A. Develop a user registration page with HTML forms to collect user information like name, email, and password.

   B. Implement client-side and server-side validation for form input.

   C. Create RESTful API endpoints in Spring Boot to handle user registration and store user data securely in the database.

2. **User Authentication:**

   A. Implement user login and authentication using React components.

   B. Use JSON Web Tokens (JWT) for secure authentication.

## Bus Ticket Booking

1. **Browse and Select Bus Routes:**

   A. Create a page for the user which allows them to enter destinations (e.g., from=... to=...).

   B. After entering the destination, browsers should navigate to the page containing bus routes, along with departure and arrival times, and pricing.

2. **Booking Process:**

   A. Develop booking forms with HTML and React components to capture user details (e.g., passenger info, seat preferences).

   B. Implement the booking logic in React to send booking requests to the Spring Boot backend using RESTful APIs.

   C. Provide users with booking confirmations and e-tickets upon successful transactions.

## User Profile and Booking History

1. **User Profile:**

   A. Create a user profile page where users can view and update their personal information.

   B. Implement features like changing passwords and managing payment methods.

2. **Booking History:**

   A. Develop a section for users to view their booking history.

   B. Retrieve booking data from the database and display it to users.

## API Endpoints

### User Registration and Authentication Endpoints

- **Register User**
  - **URL:** `/api/register`
  - **Method:** `POST`
  - **Description:** Registers a new user.
  - **Request Body:** JSON containing user details (name, email, password).
  - **Example Request:**
    ```json
    {
      "name": "John Doe",
      "email": "john.doe@example.com",
      "password": "password123"
    }
    ```
  - **Example Response:**
    ```json
    {
      "message": "User registered successfully",
      "userId": 1
    }
    ```

- **Login User**
  - **URL:** `/api/login`
  - **Method:** `POST`
  - **Description:** Authenticates a user and returns a JWT.
  - **Request Body:** JSON containing email and password.
  - **Example Request:**
    ```json
    {
      "email": "john.doe@example.com",
      "password": "password123"
    }
    ```
  - **Example Response:**
    ```json
    {
      "token": "jwt-token"
    }
    ```

### Bus Ticket Booking Endpoints

- **Get Available Bus Routes**
  - **URL:** `/api/routes`
  - **Method:** `GET`
  - **Description:** Retrieves available bus routes.
  - **Example Response:**
    ```json
    [
      {
        "routeId": 1,
        "source": "City A",
        "destination": "City B",
        "departureTime": "2024-07-14T10:00:00",
        "arrivalTime": "2024-07-14T14:00:00",
        "price": 20.0
      }
    ]
    ```

- **Book a Ticket**
  - **URL:** `/api/book`
  - **Method:** `POST`
  - **Description:** Books a ticket for a specified route.
  - **Request Body:** JSON containing booking details (route id, passenger info, seat preferences).
  - **Example Request:**
    ```json
    {
      "routeId": 1,
      "passengerName": "Jane Doe",
      "seatPreference": "Window"
    }
    ```
  - **Example Response:**
    ```json
    {
      "bookingId": 1,
      "confirmation": "Booking confirmed. E-ticket sent to email."
    }
    ```

- **Get Booking Details**
  - **URL:** `/api/bookings/{id}`
  - **Method:** `GET`
  - **Description:** Retrieves booking details by booking ID.
  - **Path Variable:** `id (long):` ID of the booking.
  - **Example Response:**
    ```json
    {
      "bookingId": 1,
      "routeId": 1,
      "passengerName": "Jane Doe",
      "seatPreference": "Window",
      "bookingStatus": "Confirmed"
    }
    ```

### User Profile and Booking History Endpoints

- **Get User Profile**
  - **URL:** `/api/user/profile`
  - **Method:** `GET`
  - **Description:** Retrieves the profile of the authenticated user.
  - **Example Response:**
    ```json
    {
      "userId": 1,
      "name": "John Doe",
      "email": "john.doe@example.com"
    }
    ```

- **Update User Profile**
  - **URL:** `/api/user/profile`
  - **Method:** `PUT`
  - **Description:** Updates the profile of the authenticated user.
  - **Request Body:** JSON containing updated user details.
  - **Example Request:**
    ```json
    {
      "name": "John Doe",
      "email": "john.doe@example.com",
      "password": "newpassword123"
    }
    ```
  - **Example Response:**
    ```json
    {
      "message": "User profile updated successfully"
    }
    ```

- **Get Booking History**
  - **URL:** `/api/user/bookings`
  - **Method:** `GET`
  - **Description:** Retrieves the booking history of the authenticated user.
  - **Example Response:**
    ```json
    [
      {
        "bookingId": 1,
        "routeId": 1,
        "passengerName": "Jane Doe",
        "seatPreference": "Window",
        "bookingStatus": "Confirmed"
      }
    ]
    ```

## Testing and Quality Assurance

**Testing:**

A. Write unit test cases and test application functionality.
```
