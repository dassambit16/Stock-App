# JobSearchPortal

JobSearchPortal is a Java Spring Boot application designed for job management. It provides various endpoints to create, read, update, and delete job listings.

## Framework and Language

- Framework: Spring Boot
- Language: Java

## Dependencies

- Spring Boot Starter Web
- Lombok
- Validation
- H2 Database
- JPA

## Data Flow

- **Job**
  1. `id` (Primary Key)
  2. `title`
  3. `description`
  4. `location`
  5. `jobSalary` (Minimum value: 20000)
  6. `companyEmail` (Must be a valid email address)
  7. `companyName`
  8. `employerName`
  9. `jobType` (Enumerated job type)

## Controllers

### Retrieve Jobs

- **GET /jobs**: Retrieve a list of all job listings.
- **GET /job/{id}**: Retrieve a job listing by its unique ID.
- **GET /jobs/type/{type}**: Retrieve job listings by a specific job type.
- **GET /jobs/salary/range/{salary}**: Retrieve job listings with salaries greater than or equal to a specified value.
- **GET /jobs/company/**: Retrieve all job listings from all companies.

### Create Jobs

- **POST /job**: Add a new job listing.
- **POST /jobs**: Add multiple job listings.

### Update Jobs

- **PUT /job/id/{id}/Salary/{salary}**: Update the salary of a job listing by its ID.
- **PUT /job/id/{id}/{loc}**: Update the location of a job listing by its ID.
- **PUT /job/id/{id}/email**: Update the email of a job listing by its ID.
- **PUT /jobs/salaryHike/jobType/{type}**: Increase the salary of job listings with a specific job type.

### Delete Jobs

- **DELETE /job/delete/id/{id}**: Remove a job listing by its ID.
- **DELETE /jobs/company/{cName}**: Remove all job listings from a specific company.

## Service

- `getAllJobs()`: Retrieve all job listings.
- `getJobById(Long id)`: Get a job listing by its unique ID.
- `postAJob(Job j)`: Add a new job listing.
- `postJobs(List<Job> j)`: Add multiple job listings.
- `updateSalaryById(Long id, Double salary)`: Update the salary of a job listing by its ID.
- `updateLocationById(Long id, String location)`: Update the location of a job listing by its ID.
- `updateEmailById(Long id, String email)`: Update the email of a job listing by its ID.
- `removeJobById(Long id)`: Remove a job listing by its ID.
- `getAllSameTypeJobs(JobType type)`: Retrieve all job listings of a specific job type.
- `getAllJobsInASalaryRange(Double salary)`: Retrieve all job listings within a specific salary range.
- `getAllJobsWithTheSameCompany(String cName)`: Retrieve all job listings from the same company.
- `removeAllJobsOfTheSameCompany(String cName)`: Remove all job listings from a specific company.
- `updateSalaryOfSimilarJobType(JobType type)`: Increase the salary of job listings with a specific job type.

## Project Summary

In this application, you can efficiently manage job listings using a variety of API endpoints. You can create new job listings, retrieve job details based on various criteria, update job information, and remove job listings when needed.

## Getting Started

To get started with this project:

1. Clone the repository to your local machine:
