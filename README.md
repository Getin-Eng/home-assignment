# Home Assignment - Onboarding week

Yet another REST, CRUD Home assignment 💼🕴️

## ☝️ Assignment router by role

- If you're a Backend Developer, please do [PHP Home Assignment](#-php-home-assignment---backend-engineer-position)
- If you're a Frontend Developer, please do [Angular 8+ Home Assignment](#%EF%B8%8F-angular-8-home-assignment---frontend-engineer-position)
- If you're a Full Stack Developer, please do [PHP Home Assignment](#-php-home-assignment---backend-engineer-position) + [Angular 8+ Home Assignment](#%EF%B8%8F-angular-8-home-assignment---frontend-engineer-position)

## 🕐 Time considerations 

Please plan your time according to the following:

- If you're a Backend Developer, it should take 3-4 hours.
- If you're a Frontend Developer, it should take 3-4 hours.
- If you're a Full Stack Developer, it should take 8-10 hours.

## Communicate your progress and questions at all time

Report your progress and your submission on [#rnd-onboarding](https://getin-xyz.slack.com/archives/C07DZ3K4FEW)

---

# 🐘 PHP Home Assignment - Backend Engineer position

> **tl;dr**☝️ **-** Need to create a REST API **without a frontend**. For employee/manager Admin panel inventory with notifications & access control

## Task summary

The task is to create a **REST API** without a frontend. The API should have features like **user management with roles**, **authentication and authorization**, **records inventory with access permissions**, and a **notification system**.

The API should allow users to **register as managers** and **create employees**. Employees should receive an **email notification** upon successful addition of records.

> **JWT tokens** should be used for authorization.

Employees can **create records** with `name` , `image` , and `category` . Managers can **see records created by their employees**. There should be **pagination** with 10 entries per page.  

Managers can **delete any record** created by their employees, while employees can **update and delete their records**. The database tables should be created using **migrations,** and the role names should be `manager` and `employee` .

> The technical requirements include **PHP 7.4+**, **Laravel 8+**, **MySQL 8**, and **queues with a database driver**. Useful Laravel features for this project include **middleware**, **HTTP requests**, **notifications**, **queues**, **Eloquent ORM**, **database pagination**, **migrations**, **seeding**, and **listener**.

* * *

## Features

1. User management with roles
2. Authentication & Authorization
3. Records inventory with access permissions
4. Notification system

## Considerations

1. The task should take 3-4 hours.
2. We seek best practices using REST API, CRUD, ORM, queue, notification, and working with composer (external dependencies).
3. Use Laravel Framework Features as much as you can

## DOD

- [ ]     Create an admin panel where the **user** can register as a manager.
- [ ]     After creation, it should be possible to create an employee.

> ❕ Create an employee model with two fields - `email address` and `password`.

- [ ]     Send an email to the employee about the successful addition. Need to use notification and send notifications via a queue.
- [ ]     authorize the manager and employee, use `jwt` token.

> An `employee` user can create a `record` with the following fields:

*   `name`
*   `image`
*   `category`

*categories as follows:*

`Full-time,
Part-time,
Contract,
Independent contractor,
Temporary,
On-call,
Volunteer`

> 💡 The list of categories must be filled in the Seeder.

- [ ]     Once created, an employee can see a list of all `records` they have created, but cannot see records other employees have created.

> 👉 There should be **10** entries per page. Use Eloquent's paginate method for pagination.

- [ ]     A manager can see a list of all records created by ONLY HIS employees.
- [ ]     The employee will see a list of all the entries in the category they have created, and the manager will see a list of all the entries in that category that their employees have created.
- [ ]     Also, the manager can see the `author` (creator) of the record and, by clicking on it, will see a list of all records of this employee (list his employee records).
- [ ]     A manager can delete any record created by his employee.
- [ ]     An employee can update and delete any of their records.

> ❗ Database tables must be created using `migration`.  
> 👉 Role names - `manager`, `employee`.

## Technical requirements:

*   PHP 8.1+
*   Laravel 9+
*   MySQL 8
*   Queues - database

### DB Schemes

1. User
2. Record

#### Useful Packages:

*   [https://packagist.org/packages/tymon/jwt-auth](https://packagist.org/packages/tymon/jwt-auth)

### Useful Laravel features:

*   Middleware
*   HTTP Requests
*   Notifications
*   Queues
*   Eloquent ORM
*   Database: Pagination
*   Database: Migrations
*   Database: Seeding
   
---

# 🛡️ Angular 8+ Home Assignment - Frontend Engineer Position

> **tl;dr**☝️ **-** Need to create a frontend consuming a REST API **without the building the API**. For employee/manager Admin panel inventory with notifications & access control
> You can refer to the above task as a reference

## Task Summary

Create an Angular 8+ application that consumes the REST API described in the PHP Laravel backend assignment. The application should provide a user interface for managers and employees to interact with the employee management system, including user authentication, record management, and viewing notifications.

## Features

1. User Authentication
2. User Registration (for managers)
3. Employee Management (for managers)
4. Record Management
5. Notification Display

## Technical Requirements

- Angular 8+
- TypeScript
- RxJS for handling asynchronous operations
- Angular Material or Bootstrap for UI components
- NgRx for state management (optional, but recommended)

## Tasks

### 1. Authentication and Authorization

- Implement a login page for both managers and employees.
- Use JWT tokens for authentication and store them securely (e.g., in local storage).
- Implement an HTTP interceptor to add the JWT token to all API requests.
- Create a guard to protect routes based on user roles.

### 2. User Registration

- Create a registration page for managers to sign up.
- Implement form validation for the registration process.

### 3. Dashboard

- Create separate dashboards for managers and employees.
- Display relevant information and quick access to main features.

### 4. Employee Management (for managers)

- Implement a page to list all employees under the manager.
- Create a form to add new employees.
- Display a confirmation message when an employee is successfully added.

### 5. Record Management

- Implement a page to list records with pagination (10 entries per page).
- Create a form to add new records with fields for name, image upload, and category selection.
- Implement record editing and deletion functionality.
- For managers, show the author of each record and provide a way to view all records of a specific employee.

### 6. Category Management

- Create a dropdown or select component for choosing record categories.
- Populate the categories from the API (seeded data from the backend).

### 7. Notifications

- Implement a notification component to display system messages (e.g., successful record creation).
- Create a notification page or modal to show all notifications for the user.

### 8. Routing

- Implement proper routing for all pages and components.
- Use route guards to protect routes based on user roles.

### 9. Error Handling

- Implement error handling for API requests and display appropriate error messages to users.

### 10. Responsive Design

- Ensure the application is responsive and works well on both desktop and mobile devices.

## Bonus Tasks

1. Implement NgRx for state management.
2. Add unit tests for components and services.
3. Implement a real-time notification system using WebSockets.

## Considerations

- The task should take approximately 4-6 hours.
- Focus on clean code, proper component structure, and adherence to Angular best practices.
- Use TypeScript features effectively, including strong typing and interfaces.
- Implement proper error handling and loading states for asynchronous operations.
- Consider using Angular's reactive forms for complex form management.

## Deliverables

1. Source code of the Angular application.
2. README file with instructions on how to set up and run the application.
3. Any additional documentation explaining your design decisions or notable features.

## Evaluation Criteria

- Code quality and organization
- Proper use of Angular features and best practices
- User interface design and usability
- Error handling and edge case management
- Responsive design implementation
- Bonus points for additional features or optimizations
