# airbnb-clone-project
The Airbnb Clone Project Blueprint

This project is tailored to enhance MY expertise in modern software development practices. By completing these tasks, I will:

Master collaborative team workflows using GitHub.
Deepen my understanding of backend architecture and database design principles.
Implement advanced security measures for API development.
Gain proficiency in designing and managing CI/CD pipelines for efficient deployment.
Strengthen my ability to document and plan complex software projects effectively.
Develop an understanding of integrating technologies like Django, MySQL, and GraphQL in a unified ecosystem.


## Team Roles

A project is a collaborative effort requiring various specialized roles:

- **Backend Developer**: Responsible for designing, building, and maintaining the server-side logic, APIs, and database interactions.
- **Frontend Developer**: Builds the user interface and ensures a seamless user experience.
- **Database Administrator (DBA)**: Manages the setup, tuning, and maintenance of the project's databases.
- **DevOps Engineer**: Implements CI/CD pipelines, manages deployments, and ensures infrastructure reliability.
- **Project Manager**: Coordinates team efforts, timelines, and communication across the project.

Each role ensures that the application is robust, scalable, and maintainable throughout the development lifecycle.


## Technology Stack

The backend for the Airbnb Clone project utilizes a range of technologies to ensure scalability, maintainability, and performance. Below is a list of the core technologies and their purpose in the project:

- **Django**: A high-level Python web framework used to build and organize the core backend functionalities and API logic.
- **Django REST Framework (DRF)**: A powerful toolkit built on Django for building RESTful APIs, handling serialization, authentication, and permissions.
- **PostgreSQL**: A robust relational database used to store and manage structured application data such as users, properties, and bookings.
- **GraphQL**: A flexible query language that allows clients to request exactly the data they need, improving performance and developer experience.
- **Celery**: An asynchronous task queue used to manage background tasks like sending notifications or processing long-running jobs (e.g., payments).
- **Redis**: An in-memory data structure store used to support caching and as a message broker for Celery tasks.
- **Docker**: A containerization platform that ensures consistency across development, testing, and production environments.
- **CI/CD Pipelines**: Automates testing, building, and deploying of code changes to reduce manual effort and improve deployment speed.


## Database Design

The database schema for the Airbnb Clone project is designed to manage users, properties, bookings, reviews, and payments efficiently. Below are the key entities and their important fields, along with their relationships:

### 🧑 Users
- `id`: Unique identifier for the user.
- `name`: Full name of the user.
- `email`: Email address (used for login).
- `password`: Hashed password for authentication.
- `user_type`: Identifies whether the user is a host or a guest.

### 🏠 Properties
- `id`: Unique identifier for the property.
- `owner_id`: Foreign key linking to the User who owns the property.
- `title`: Name or short description of the property.
- `location`: City or region where the property is located.
- `price_per_night`: Rental cost per night.

### 📅 Bookings
- `id`: Unique identifier for the booking.
- `user_id`: Foreign key linking to the User who made the booking.
- `property_id`: Foreign key linking to the booked Property.
- `start_date`: Start date of the booking.
- `end_date`: End date of the booking.

### 💳 Payments
- `id`: Unique identifier for the payment.
- `booking_id`: Foreign key linking to the related Booking.
- `amount`: Total payment amount.
- `payment_status`: Status of the payment (e.g., pending, completed).
- `payment_date`: Date the payment was processed.

### 📝 Reviews
- `id`: Unique identifier for the review.
- `user_id`: Foreign key linking to the User who wrote the review.
- `property_id`: Foreign key linking to the reviewed Property.
- `rating`: Numeric rating (e.g., 1–5 stars).
- `comment`: Textual feedback from the user.

### 🔗 Relationships
- A **User** can own multiple **Properties**.
- A **User** can make multiple **Bookings**.
- A **Property** can have many **Bookings** and **Reviews**.
- Each **Booking** is linked to one **User** and one **Property**.
- A **Payment** is associated with a **Booking**.
- A **Review** is made by a **User** and linked to a **Property**.
