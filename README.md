#  Amritsar Tourism

#  Overview

Amritsar Tourism is a web application built with Spring Boot, Thymeleaf, and Bootstrap, designed to facilitate hotel bookings in Amritsar. Users can browse hotels, view room details, and book rooms by selecting check-in/check-out dates and the number of guests. Admins can manage hotel rooms via a dedicated panel.

#  Features

#  User Features:
- Browse available hotels with details (name, description, rating, starting price, image).
- Book a hotel by selecting check-in/check-out dates, number of adults/children, and view total cost.
- Receive confirmation messages after successful bookings.

#  Admin Features:
- Add new rooms and associate them with hotels.
- View success/error messages for admin actions.

# Security:
- CSRF protection for form submissions.
- Input validation for both user and admin forms.

# Technologies Used
- **Backend:** Spring Boot, Spring Data JPA, Hibernate
- **Frontend:** Thymeleaf, Bootstrap 5.3.3, HTML, CSS, JavaScript
- **Database:** MySQL/PostgreSQL (configurable via `application.properties`)
- **Build Tool:** Maven
- **Validation:** Jakarta Bean Validation
- **Logging:** SLF4J (recommended)

# Prerequisites
- Java 17 or higher
- Maven 3.6.0 or higher
- A relational database (e.g., MySQL, PostgreSQL)
- IDE (e.g., IntelliJ IDEA, Eclipse, VS Code)

#Setup Instructions

# 1. Clone the Repository
```bash
git clone https://github.com/Vandanarajput/Amritsar_Tourism.git
cd Amritsar_Tourism
```

# 2. Configure the Database

Create a database in your DBMS (e.g., MySQL):
```sql
CREATE DATABASE amritsar_tourism;
```

Update `src/main/resources/application.properties`:
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/amritsar_tourism
spring.datasource.username=your-username
spring.datasource.password=your-password
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.format_sql=true
```

# 3. Build the Project
```bash
mvn clean install
```

# 4. Run the Application
```bash
mvn spring-boot:run
```

Access the application at [http://localhost:8080](http://localhost:8080).

# 5. Access the Application
- **User Interface:** [http://localhost:8080/accommodation](http://localhost:8080/accommodation)
- **Admin Panel:** [http://localhost:8080/admin/addroom](http://localhost:8080/admin/addroom)

 _Note: Secure admin routes in production with Spring Security._

#  Project Structure
```
amritsar-tourism/
├── src/
│   └── main/
│       ├── java/
│       │   └── com/mgcfgs/amritsartourism/amritsar_tourism/
│       │       ├── controller/
│       │       ├── model/
│       │       ├── repository/
│       │       ├── service/
│       │       └── config/
│       ├── resources/
│       │   ├── templates/
│       │   │   ├── home/
│       │   │   ├── admin/
│       │   │   ├── user/
│       │   │   └── fragments/
│       │   ├── static/
│       │   │   ├── css/
│       │   │   └── img/
│       │   └── application.properties
├── pom.xml
└── README.md
```

# Usage

# For Users
1. Go to [http://localhost:8080/accommodation](http://localhost:8080/accommodation)
2. Browse and select a hotel.
3. Click “Book Now” and fill out booking details.
4. Submit and receive confirmation.

# For Admins
1. Go to [http://localhost:8080/admin/addroom](http://localhost:8080/admin/addroom)
2. Fill in room details and assign to a hotel.
3. Submit the form and check the success/error message.

# Database Schema

Tables generated (via Hibernate):
- `hotel` – Hotel details
- `room` – Room details
- `booking` – Booking records with references to users and rooms

# Future Improvements
- Integrate Spring Security for user roles (admin/user)
- Booking confirmation page with summary
- Room selection interface
- Admin dashboard for analytics and booking management
- Add unit and integration tests

# Troubleshooting
- **TransientPropertyValueException:** Make sure related entities (e.g., Hotel in Room) are loaded from the DB before saving.
- **Connection Issues:** Double-check DB URL, credentials, and running status.

# Contributing
1. Fork the repository
2. Create a new branch (`git checkout -b feature/your-feature`)
3. Make changes and commit (`git commit -m "Add feature"`)
4. Push and create a pull request

# License
This project is licensed under the MIT License. See `LICENSE` for more details.

# Contact
For project-related inquiries, contact **vandanakashyap674@gmail.com**
