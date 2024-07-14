# Bus Ticket Booking System

## Demo Video

[![Watch the video](https://i.vimeocdn.com/video/983580502.jpg)](https://vimeo.com/983860280)

## Table of Contents

1. [Setting up Backend (Spring Boot)](#setting-up-backend-spring-boot)
2. [Setting Up Frontend (HTML, CSS, and JS or Thymeleaf Template)](#setting-up-frontend-html-css-and-js-or-thymeleaf-template)
3. [User Registration and Authentication](#user-registration-and-authentication)
4. [Bus Ticket Booking](#bus-ticket-booking)
5. [User Profile and Booking History](#user-profile-and-booking-history)
6. [API Endpoints](#api-endpoints)
7. [Testing and Quality Assurance](#testing-and-quality-assurance)
8. [Additional Resources](#additional-resources)

## Setting up Backend (Spring Boot)

1. **Initialize Spring Boot Project**
   - Set up a new Spring Boot application.

2. **Define Entities**
   - Create entities such as Bus, Booking, and Passenger and configure the data models.

3. **Create RESTful APIs**
   - Develop RESTful APIs using Spring Boot controllers to handle operations like booking requests, user authentication, and database interactions.

4. **Database Setup**
   - Configure a database (e.g., MySQL, MongoDB) to store bus schedules, booking details, and user information.

## Setting Up Frontend (HTML, CSS, and JS or Thymeleaf Template)

1. **Design User Interface**
   - Design the application's user interface using HTML, JavaScript, and CSS. Create responsive web pages for displaying bus routes, booking forms, and user profiles.

2. **Use CSS Frameworks**
   - Apply CSS frameworks such as Bootstrap to enhance the user experience and make the UI more appealing.

## User Registration and Authentication

1. **User Registration:**
   - Develop registration forms using HTML to collect user details like name, email, and password.
   - Implement both client-side and server-side validation for form inputs.
   - Set up RESTful API endpoints in Spring Boot to handle registration requests and securely store user data.

2. **User Authentication:**
   - Implement login functionality using React components.
   - Use JSON Web Tokens (JWT) for secure user authentication.

## Bus Ticket Booking

1. **Search and Select Bus Routes:**
   - Create a page where users can enter their departure and destination locations.
   - After submitting the destinations, navigate to a page that displays available bus routes, departure and arrival times, and ticket prices.

2. **Booking Process:**
   - Develop booking forms using HTML and React to capture user details like passenger information and seat preferences.
   - Implement booking logic in React to send requests to the Spring Boot backend via RESTful APIs.
   - Provide users with booking confirmations and e-tickets after successful transactions.

## User Profile and Booking History

1. **User Profile:**
   - Create a profile page where users can view and update their personal information.
   - Include features for changing passwords and managing payment methods.

2. **Booking History:**
   - Develop a section where users can view their past bookings.
   - Retrieve booking data from the database and display it to users.

## API Endpoints

### User Registration and Authentication Endpoints

- **Register User**
  - **Endpoint:** `/api/register`
  - **Method:** `POST`
  - **Description:** Register a new user.
  - **Request Body:** JSON containing user information (name, email, password).
  - **Example Request:**
    ```json
    {
      "name": "Jane Smith",
      "email": "jane.smith@example.com",
      "password": "securepassword"
    }
    ```
  - **Example Response:**
    ```json
    {
      "message": "Registration successful",
      "userId": 1
    }
    ```

- **Login User**
  - **Endpoint:** `/api/login`
  - **Method:** `POST`
  - **Description:** Authenticate a user and provide a JWT.
  - **Request Body:** JSON with email and password.
  - **Example Request:**
    ```json
    {
      "email": "jane.smith@example.com",
      "password": "securepassword"
    }
    ```
  - **Example Response:**
    ```json
    {
      "token": "jwt-token"
    }
    ```

### Bus Ticket Booking Endpoints

- **Fetch Available Bus Routes**
  - **Endpoint:** `/api/routes`
  - **Method:** `GET`
  - **Description:** Get a list of available bus routes.
  - **Example Response:**
    ```json
    [
      {
        "routeId": 1,
        "source": "City X",
        "destination": "City Y",
        "departureTime": "2024-07-14T08:00:00",
        "arrivalTime": "2024-07-14T12:00:00",
        "price": 25.0
      }
    ]
    ```

- **Book a Ticket**
  - **Endpoint:** `/api/book`
  - **Method:** `POST`
  - **Description:** Make a booking for a specified route.
  - **Request Body:** JSON with booking details (route ID, passenger information, seat preferences).
  - **Example Request:**
    ```json
    {
      "routeId": 1,
      "passengerName": "John Doe",
      "seatPreference": "Aisle"
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
  - **Endpoint:** `/api/bookings/{id}`
  - **Method:** `GET`
  - **Description:** Retrieve details of a specific booking by ID.
  - **Path Variable:** `id (long):` The ID of the booking.
  - **Example Response:**
    ```json
    {
      "bookingId": 1,
      "routeId": 1,
      "passengerName": "John Doe",
      "seatPreference": "Aisle",
      "bookingStatus": "Confirmed"
    }
    ```

### User Profile and Booking History Endpoints

- **Get User Profile**
  - **Endpoint:** `/api/user/profile`
  - **Method:** `GET`
  - **Description:** Fetch the authenticated user's profile.
  - **Example Response:**
    ```json
    {
      "userId": 1,
      "name": "Jane Smith",
      "email": "jane.smith@example.com"
    }
    ```

- **Update User Profile**
  - **Endpoint:** `/api/user/profile`
  - **Method:** `PUT`
  - **Description:** Update the authenticated user's profile.
  - **Request Body:** JSON with updated user information.
  - **Example Request:**
    ```json
    {
      "name": "Jane Smith",
      "email": "jane.smith@example.com",
      "password": "newsecurepassword"
    }
    ```
  - **Example Response:**
    ```json
    {
      "message": "Profile updated successfully"
    }
    ```

- **Get Booking History**
  - **Endpoint:** `/api/user/bookings`
  - **Method:** `GET`
  - **Description:** Fetch the authenticated user's booking history.
  - **Example Response:**
    ```json
    [
      {
        "bookingId": 1,
        "routeId": 1,
        "passengerName": "John Doe",
        "seatPreference": "Aisle",
        "bookingStatus": "Confirmed"
      }
    ]
    ```

## Testing and Quality Assurance

### Testing:

1. **Write Unit Tests**
   - Develop unit tests to verify the functionality of different components of the application.

2. **Test Application Functionality**
   - Perform comprehensive testing to ensure the application works as expected.

## Additional Resources

- **Email and Ticketing System**
  - For details on the email and ticketing system, refer to the video tutorial provided above. This feature includes sending emails and e-tickets upon successful bookings.
  
- **PDF Documentation**
  - Additional documentation is available in the PDF file included in the repository.
