# University Management System Backend

The **PH University Management Project** is a comprehensive backend system designed to manage a university's core functionalities, including user authentication, profile management, academic processes, and administrative operations. This project is built to cater to three primary roles: **Students**, **Faculty**, and **Admin**, each with distinct access and capabilities.

## Features

### Authentication
- Secure login and logout for all user roles.
- Password update functionality for Students, Faculty, and Admins.

### Profile Management
- **Students**: Manage and update their profiles with editable fields.
- **Faculty**: Manage and update their profiles with editable fields.
- **Admins**: Manage and update their profiles with editable fields.

### Academic Process
- **Students**:
  - Enroll in offered courses for a specific semester.
  - View class schedules, grades, notice boards, and events.
- **Faculty**:
  - Manage student grades and access personal and academic information.
- **Admins**:
  - Manage semesters, courses, offered courses, sections, rooms, and buildings.

### User Management
- **Admins**:
  - Manage user accounts, including creating, blocking/unblocking users, and changing passwords.

---

## Data Model

### **User**
| Field             | Description                          |
|--------------------|--------------------------------------|
| `_id`             | Unique identifier                   |
| `id`              | Auto-generated user ID              |
| `password`        | Encrypted password                  |
| `needsPasswordChange` | Indicates if the user must change their password |
| `role`            | Role of the user (`Student`, `Faculty`, `Admin`) |
| `status`          | Active or inactive status           |
| `isDeleted`       | Soft delete flag                    |
| `createdAt`       | Timestamp of creation               |
| `updatedAt`       | Timestamp of the last update        |

### **Student**
| Field             | Description                          |
|--------------------|--------------------------------------|
| `_id`             | Unique identifier                   |
| `id`              | Auto-generated student ID           |
| `name`            | Full name                           |
| `gender`          | Gender                              |
| `dateOfBirth`     | Date of birth                       |
| `email`           | Email address                       |
| `contactNo`       | Contact number                      |
| `emergencyContactNo` | Emergency contact number         |
| `presentAddress`  | Current address                     |
| `permanentAddress`| Permanent address                   |
| `guardian`        | Guardian information                |
| `localGuardian`   | Local guardian information          |
| `profileImage`    | Profile image URL                   |
| `admissionSemester`| Semester of admission              |
| `isDeleted`       | Soft delete flag                    |
| `createdAt`       | Timestamp of creation               |
| `updatedAt`       | Timestamp of the last update        |

### **Faculty**
| Field             | Description                          |
|--------------------|--------------------------------------|
| `_id`             | Unique identifier                   |
| `id`              | Auto-generated faculty ID           |
| `designation`     | Designation                         |
| `name`            | Full name                           |
| `gender`          | Gender                              |
| `dateOfBirth`     | Date of birth                       |
| `email`           | Email address                       |
| `contactNo`       | Contact number                      |
| `academicFaculty` | Associated academic faculty         |
| `academicDepartment` | Associated academic department   |
| `isDeleted`       | Soft delete flag                    |
| `createdAt`       | Timestamp of creation               |
| `updatedAt`       | Timestamp of the last update        |

### **Admin**
| Field             | Description                          |
|--------------------|--------------------------------------|
| `_id`             | Unique identifier                   |
| `id`              | Auto-generated admin ID             |
| `designation`     | Designation                         |
| `name`            | Full name                           |
| `gender`          | Gender                              |
| `dateOfBirth`     | Date of birth                       |
| `email`           | Email address                       |
| `contactNo`       | Contact number                      |
| `managementDepartment` | Associated management department |
| `isDeleted`       | Soft delete flag                    |
| `createdAt`       | Timestamp of creation               |
| `updatedAt`       | Timestamp of the last update        |

### **Academic Semester**
| Field         | Description                  |
|---------------|------------------------------|
| `_id`         | Unique identifier           |
| `name`        | Name of the semester         |
| `year`        | Year of the semester         |
| `code`        | Unique code for the semester |
| `startMonth`  | Start month                  |
| `endMonth`    | End month                    |
| `createdAt`   | Timestamp of creation        |
| `updatedAt`   | Timestamp of the last update |

---

## API Endpoints

### **User**
- **POST** `/users/create-student` - Create a new student.
- **POST** `/users/create-faculty` - Create a new faculty.
- **POST** `/users/create-admin` - Create a new admin.

### **Student**
- **GET** `/students` - Fetch all students.
- **GET** `/students/:id` - Fetch a specific student by ID.
- **PATCH** `/students/:id` - Update a specific student's information.
- **DELETE** `/students/:id` - Delete a specific student.
- **GET** `/students/my-profile` - Fetch the logged-in student's profile.

### **Faculty**
- **GET** `/faculties` - Fetch all faculty members.
- **GET** `/faculties/:id` - Fetch a specific faculty member by ID.
- **PATCH** `/faculties/:id` - Update a specific faculty member's information.
- **DELETE** `/faculties/:id` - Delete a specific faculty member.
- **GET** `/faculties/my-profile` - Fetch the logged-in faculty member's profile.

### **Admin**
- **GET** `/admins` - Fetch all admins.
- **GET** `/admins/:id` - Fetch a specific admin by ID.
- **PATCH** `/admins/:id` - Update a specific admin's information.
- **DELETE** `/admins/:id` - Delete a specific admin.
- **GET** `/admins/my-profile` - Fetch the logged-in admin's profile.

### **Auth**
- **POST** `/auth/login` - Log in to the system.
- **POST** `/auth/refresh-token` - Refresh authentication tokens.
- **POST** `/auth/change-password` - Change the current password.
- **POST** `/auth/forgot-password` - Initiate password recovery.
- **POST** `/auth/reset-password` - Reset a forgotten password.

---

## Technologies Used
- **Node.js**: Backend runtime environment.
- **Express.js**: Web framework for building APIs.
- **TypeScript**: Enhances code reliability with static typing.
- **MongoDB**: NoSQL database for managing university data.

---

## License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).

---

## Contributing

We welcome contributions! Please fork this repository, create a feature branch, and submit a pull request for review.

---

## Acknowledgements

Special thanks to the contributors and the open-source community for their support in making this project successful.
