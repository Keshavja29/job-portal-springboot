# Job Portal Application

Enterprise-grade Job Portal built with Java Spring Boot, featuring role-based access control, job management, and application tracking.

## Features

- **User Management** - Job Seekers & Employers with role-based access
- **Job Listings** - Post, search, and filter jobs
- **Application Management** - Apply for jobs, track applications
- **Resume Upload** - PDF/DOC resume support
- **Company Profiles** - Company information and branding
- **Advanced Search** - Filter by location, salary, experience
- **Email Notifications** - Application status updates
- **Admin Dashboard** - Manage users, jobs, and applications
- **RESTful API** - Complete REST API with Swagger docs

## Tech Stack

- Java 17
- Spring Boot 3.1
- Spring Security (JWT Authentication)
- Spring Data JPA
- MySQL / PostgreSQL
- Maven
- Swagger/OpenAPI
- Lombok

## Architecture

- **Controller Layer** - REST endpoints
- **Service Layer** - Business logic
- **Repository Layer** - Data access
- **Security Layer** - JWT authentication & authorization
- **DTO Pattern** - Data transfer objects

## Installation

### Prerequisites
- Java 17+
- Maven 3.8+
- MySQL 8.0+

### Setup

```bash
# Clone repository
git clone https://github.com/Keshavja29/job-portal-springboot.git
cd job-portal-springboot

# Configure database in application.properties
# Update MySQL credentials

# Build project
mvn clean install

# Run application
mvn spring-boot:run
```

Application runs on: `http://localhost:8080`

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register user
- `POST /api/auth/login` - Login user
- `POST /api/auth/refresh` - Refresh token

### Jobs
- `GET /api/jobs` - List all jobs
- `POST /api/jobs` - Create job (Employer only)
- `GET /api/jobs/{id}` - Get job details
- `PUT /api/jobs/{id}` - Update job (Employer only)
- `DELETE /api/jobs/{id}` - Delete job (Employer only)
- `GET /api/jobs/search` - Search jobs

### Applications
- `POST /api/applications` - Apply for job
- `GET /api/applications/user` - Get user's applications
- `GET /api/applications/job/{jobId}` - Get job applications (Employer)
- `PUT /api/applications/{id}/status` - Update status (Employer)

### Companies
- `GET /api/companies` - List companies
- `POST /api/companies` - Create company profile
- `GET /api/companies/{id}` - Get company details

### Users
- `GET /api/users/profile` - Get user profile
- `PUT /api/users/profile` - Update profile
- `POST /api/users/resume` - Upload resume

## Database Schema

### Users Table
- id, username, email, password, role, created_at

### Jobs Table
- id, title, description, company_id, location, salary, experience, created_at

### Applications Table
- id, job_id, user_id, resume_url, status, applied_at

### Companies Table
- id, name, description, website, logo_url, created_at

## Configuration

```properties
# application.properties
spring.datasource.url=jdbc:mysql://localhost:3306/jobportal
spring.datasource.username=root
spring.datasource.password=yourpassword
spring.jpa.hibernate.ddl-auto=update
jwt.secret=your-secret-key
jwt.expiration=86400000
```

## API Documentation

Swagger UI: `http://localhost:8080/swagger-ui.html`

## Security

- JWT-based authentication
- Role-based authorization (ROLE_USER, ROLE_EMPLOYER, ROLE_ADMIN)
- Password encryption with BCrypt
- CORS configuration

## Testing

```bash
mvn test
```

## Future Enhancements

- Real-time chat between employers and candidates
- Video interview scheduling
- Skill assessment tests
- Job recommendations using ML
- Analytics dashboard
- Mobile app

## License

MIT License

---

**Made with ❤️ by Keshav**
