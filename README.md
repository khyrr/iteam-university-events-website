# iTeam University Event Management Platform

<div align="center">

<img width="919" height="307" alt="image" src="https://github.com/user-attachments/assets/c1d428a0-911d-4a8c-9d54-627eafc99ab7" />


**A comprehensive event management and job placement platform for universities**

[![PHP](https://img.shields.io/badge/PHP-8.2+-777BB4?style=flat&logo=php&logoColor=white)](https://www.php.net/)
[![MySQL](https://img.shields.io/badge/MySQL-10.4+-4479A1?style=flat&logo=mysql&logoColor=white)](https://www.mysql.com/)
[![TailwindCSS](https://img.shields.io/badge/TailwindCSS-3.0+-06B6D4?style=flat&logo=tailwindcss&logoColor=white)](https://tailwindcss.com/)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?style=flat&logo=javascript&logoColor=black)](https://www.javascript.com/)

</div>

---

## 📋 Table of Contents

- [About](#-about)
- [Key Features](#-key-features)
- [Technologies Used](#-technologies-used)
- [System Architecture](#-system-architecture)
- [Installation](#-installation)
- [Database Schema](#-database-schema)
- [Project Structure](#-project-structure)
- [API Endpoints](#-api-endpoints)
- [Usage Guide](#-usage-guide)
- [Contributing](#-contributing)
- [License](#-license)
- [Contact & Support](#-contact--support)

---

## 🎯 About

The **iTeam University Event Management Platform** is a modern, full-featured web application designed to streamline campus event management and job placement activities. The platform connects three key stakeholders:

- **Students**: Browse events, register for activities, apply for job opportunities
- **Organizations**: Create and manage events, post job offers, track applications
- **Administrators**: Oversee platform operations, manage users, moderate content

Built with a mobile-first approach using TailwindCSS, the platform features dark mode support, real-time notifications, calendar integration, and comprehensive analytics.

---

## ✨ Key Features

### For Students
- 📅 **Event Discovery**: Browse and filter upcoming events by category, date, and location
- ✅ **Event Registration**: Easy registration with approval workflows
- 💼 **Job Opportunities**: Access internships and job postings from partner organizations
- 📄 **Application Management**: Submit applications with resume uploads and cover letters
- 🔔 **Notifications**: Real-time updates on registrations, events, and applications
- 📊 **Personal Dashboard**: Track registrations, applications, and event history
- 🌙 **Dark Mode**: Comfortable viewing in low-light environments

### For Organizations
- 🎪 **Event Creation**: Create and manage workshops, conferences, webinars, and career fairs
- 📸 **Event Gallery**: Upload and manage event photos
- 📋 **Registration Management**: Track attendees and approve registrations
- 💼 **Job Posting**: Post full-time, part-time, contract, and internship positions
- 👥 **Application Review**: Review candidate applications and manage hiring pipeline
- 📈 **Analytics Dashboard**: Insights on event attendance and application metrics
- 📅 **Calendar Integration**: Google Calendar sync for events

### For Administrators
- 👤 **User Management**: Manage students and organizations with approval workflows
- 🎯 **Event Moderation**: Review and moderate all platform events
- 🖼️ **Gallery Management**: Manage platform-wide image gallery
- 📊 **System Analytics**: Comprehensive dashboards for platform metrics
- 🔍 **Search & Filter**: Advanced search across all entities
- 🔔 **Notification System**: Broadcast announcements to users
- 🛡️ **Access Control**: Role-based permissions and security management

---

## 🛠 Technologies Used

### Frontend
- **HTML5**: Semantic markup and structure
- **TailwindCSS 3.x**: Utility-first CSS framework via CDN
- **JavaScript ES6+**: Modern JavaScript features
- **Responsive Design**: Mobile-first approach

### Backend
- **PHP 8.2+**: Server-side scripting
- **MySQL/MariaDB 10.4+**: Relational database management
- **PDO**: Secure database connections with prepared statements
- **Session Management**: Secure authentication and authorization

### Additional Tools & Libraries
- **bcrypt**: Password hashing and security
- **Google Calendar API**: Calendar integration
- **File Upload System**: Resume and image management
- **RESTful API**: JSON-based API architecture

---

## 🏗 System Architecture

```
┌─────────────────────────────────────────────────────────┐
│                    Client Browser                        │
│              (HTML, CSS, JavaScript)                     │
└────────────────────┬────────────────────────────────────┘
                     │ HTTP/HTTPS
                     ▼
┌─────────────────────────────────────────────────────────┐
│                  Apache Web Server                       │
│                  (XAMPP/LAMP/WAMP)                      │
└────────────────────┬────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────────┐
│              PHP Backend (API Layer)                     │
│  ┌──────────┬──────────────┬────────────┬───────────┐  │
│  │ Student  │ Organization │   Admin    │  Backend  │  │
│  │   API    │     API      │    API     │    API    │  │
│  └──────────┴──────────────┴────────────┴───────────┘  │
└────────────────────┬────────────────────────────────────┘
                     │ PDO
                     ▼
┌─────────────────────────────────────────────────────────┐
│              MySQL/MariaDB Database                      │
│                 (event_management)                       │
└─────────────────────────────────────────────────────────┘
```

---

## 💻 Installation

### Prerequisites

- **PHP**: 8.0 or higher
- **MySQL/MariaDB**: 10.4 or higher
- **Apache**: 2.4 or higher (XAMPP/LAMP/WAMP recommended)
- **Web Browser**: Modern browser with JavaScript enabled

### Step-by-Step Installation

#### 1. Clone the Repository

```bash
git clone https://github.com/0xkhyr/iteam-university-events-website.git
cd iteam-university-events-website
```

#### 2. Set Up Web Server

Move the project to your web server directory:

```bash
# For XAMPP on Linux
sudo mv iteam-university-website /opt/lampp/htdocs/

# For XAMPP on Windows
# Move to C:\xampp\htdocs\

# For LAMP on Ubuntu
sudo mv iteam-university-website /var/www/html/
```

#### 3. Configure Database

**Option A: Automatic Setup (Recommended)**

1. Start your MySQL/MariaDB server
2. Navigate to: `http://localhost/iteam-university-website/backend/db/setup_database.php`
3. The script will automatically create the database and tables

**Option B: Manual Setup**

```bash
# Login to MySQL
mysql -u root -p

# Create database
CREATE DATABASE event_management;

# Import schema
mysql -u root -p event_management < backend/db/init_db.sql
```

#### 4. Configure Database Connection

Edit the database connection files:

```php
// backend/db/db_connection.php
// admin/api/db_connection.php
// student/api/db_connection.php
// organization/api/db_connection.php

$host = 'localhost';
$dbname = 'event_management';
$username = 'root';  // Change if needed
$password = '';      // Change if needed
```

#### 5. Set Permissions

```bash
# For Linux/Mac
chmod -R 755 /var/www/html/iteam-university-website
chmod -R 777 /var/www/html/iteam-university-website/frontend/uploads
```

#### 6. Access the Application

- **Homepage**: `http://localhost/iteam-university-website/`
- **Student Portal**: `http://localhost/iteam-university-website/student/`
- **Organization Portal**: `http://localhost/iteam-university-website/organization/`
- **Admin Portal**: `http://localhost/iteam-university-website/admin/`

#### 7. Default Login Credentials

**Admin:**
- Email: `admin@iteamuniversity.com`
- Password: `admin123` (change after first login)

**Test Student:**
- Register through: `http://localhost/iteam-university-website/auth/signup.html`

**Test Organization:**
- Register through: `http://localhost/iteam-university-website/organization/auth/singup.html`

---

## 🗄 Database Schema

The platform uses a relational database with the following main tables:

### Core Tables

#### `accounts`
Central authentication table linking all user types
- `account_id` (PK)
- `account_type` (student/organization/admin)
- `reference_id` (FK to respective table)
- `last_login`, `created_at`, `updated_at`

#### `students`
Student user information
- `student_id` (PK)
- `first_name`, `last_name`, `email`, `password`
- `profile_picture`, `status`, `registration_date`

#### `organizations`
Organization profiles
- `organization_id` (PK)
- `name`, `email`, `password`, `description`
- `profile_picture`, `status`, `registration_date`

#### `admins`
Administrator accounts
- `admin_id` (PK)
- `username`, `email`, `password`
- `created_at`, `updated_at`

### Event Management

#### `events`
Event information
- `event_id` (PK)
- `title`, `description`, `location`
- `start_date`, `end_date`
- `event_type` (workshop/conference/fair/webinar)
- `max_capacity`, `organizer_id` (FK)
- `thumbnail_url`, `requires_approval`

#### `event_registrations`
Student event registrations
- `registration_id` (PK)
- `event_id` (FK), `student_id` (FK)
- `registration_date`
- `status` (pending/confirmed/cancelled)

#### `event_gallery`
Event photo gallery
- `image_id` (PK)
- `event_id` (FK)
- `image_url`, `caption`, `upload_date`

### Job Management

#### `job_offers`
Job postings by organizations
- `job_offer_id` (PK)
- `organization_id` (FK)
- `title`, `description`
- `job_type` (full-time/part-time/contract/internship)
- `status` (active/filled/expired/draft)
- `posted_date`, `expiry_date`

#### `job_applications`
Student job applications
- `application_id` (PK)
- `job_offer_id` (FK), `student_id` (FK)
- `cover_letter`, `resume_path`
- `status` (pending/reviewed/shortlisted/rejected/accepted)
- `application_date`, `notes`

### Notifications

#### `notifications`
System notifications
- `notification_id` (PK)
- `account_id` (FK), `event_id` (FK)
- `notification_type` (confirmation/reminder/cancellation/etc.)
- `message`, `is_read`, `send_date`

### Database Relationships

```
accounts (1) ──< (N) notifications
    │
    ├── student (1:1) ──< (N) event_registrations ──> (1) events
    │                  └── (N) job_applications ──> (1) job_offers
    │
    ├── organization (1:1) ──< (N) events
    │                        └── (N) job_offers
    │
    └── admin (1:1)

events (1) ──< (N) event_gallery
           └── (N) event_registrations
```

---

## 📁 Project Structure

```
iteam-university-website/
│
├── index.html                      # Main landing page
│
├── admin/                          # Admin portal
│   ├── index.html                  # Admin dashboard entry
│   ├── dash.js                     # Dashboard logic
│   ├── router.js                   # Client-side routing
│   ├── main.js                     # Main JavaScript
│   ├── style.css                   # Admin-specific styles
│   │
│   ├── api/                        # Admin API endpoints
│   │   ├── adminlogin.php          # Admin authentication
│   │   ├── dashboard_data.php      # Dashboard statistics
│   │   ├── students.php            # Student management
│   │   ├── organizations.php       # Organization management
│   │   ├── events.php              # Event moderation
│   │   ├── notifications.php       # Notification system
│   │   ├── gallery_photos.php      # Gallery management
│   │   └── ...
│   │
│   ├── auth/
│   │   └── admin-login.html        # Admin login page
│   │
│   └── views/                      # Admin view templates
│       ├── dashboard.html
│       ├── students.html
│       ├── events.html
│       ├── organizations.html
│       └── ...
│
├── student/                        # Student portal
│   ├── README.md                   # Student module docs
│   │
│   ├── api/                        # Student API endpoints
│   │   ├── auth.php                # Student authentication
│   │   ├── events.php              # Event browsing/registration
│   │   ├── job-offers.php          # Job listings
│   │   ├── job-applications.php    # Application management
│   │   ├── profile.php             # Profile management
│   │   └── ...
│   │
│   ├── auth/
│   │   ├── login.html              # Student login
│   │   └── register.html           # Student registration
│   │
│   ├── components/                 # Reusable components
│   │   ├── footer.html
│   │   └── ...
│   │
│   ├── css/
│   │   ├── output.css              # Compiled Tailwind CSS
│   │   ├── tailwind.css            # Tailwind config
│   │   └── styles.css              # Custom styles
│   │
│   ├── js/                         # JavaScript modules
│   │
│   └── pages/                      # Student pages
│       ├── index.html              # Student dashboard
│       ├── events.html             # Event listing
│       ├── event-details.html      # Event details
│       ├── my-registrations.html   # Registration history
│       ├── job-offers.html         # Job listings
│       ├── my-applications.html    # Application tracking
│       └── ...
│
├── organization/                   # Organization portal
│   ├── README.md                   # Organization module docs
│   │
│   ├── api/                        # Organization API endpoints
│   │   ├── auth.php                # Organization authentication
│   │   ├── events.php              # Event management
│   │   ├── registrations.php       # Registration management
│   │   ├── job-offers.php          # Job posting
│   │   ├── applications.php        # Application review
│   │   ├── analytics.php           # Analytics data
│   │   └── ...
│   │
│   ├── auth/
│   │   ├── login.html              # Organization login
│   │   └── singup.html             # Organization registration
│   │
│   ├── components/                 # Reusable components
│   │   ├── sidebar.html
│   │   ├── topnav.html
│   │   └── ...
│   │
│   ├── css/
│   │   ├── output.css
│   │   ├── tailwind.css
│   │   └── styles.css
│   │
│   ├── js/                         # JavaScript modules
│   │
│   └── pages/                      # Organization pages
│       ├── dashboard.html          # Organization dashboard
│       ├── events.html             # Event management
│       ├── registrations.html      # Registration tracking
│       ├── job-offers.html         # Job posting management
│       ├── applications.html       # Application review
│       ├── analytics.html          # Analytics dashboard
│       └── ...
│
├── backend/                        # Shared backend
│   ├── api/                        # Shared API utilities
│   │   ├── auth/
│   │   │   ├── auth.php            # Common auth functions
│   │   │   └── singup.php          # Registration handler
│   │   └── ...
│   │
│   └── db/                         # Database setup
│       ├── init_db.sql             # Database schema & seed data
│       ├── setup_database.php      # Automated setup script
│       ├── db_connection.php       # PDO connection handler
│       ├── db_config.php           # Configuration
│       └── functions.php           # Database utility functions
│
├── frontend/                       # Shared frontend assets
│   ├── assets/
│   │   ├── images/                 # Images and icons
│   │   └── fonts/                  # Custom fonts
│   │
│   ├── css/
│   │   ├── styles.css              # Global styles
│   │   └── tailwind.css            # Tailwind configuration
│   │
│   ├── js/
│   │   ├── config.js               # Path configuration
│   │   ├── auth-guard.js           # Route protection
│   │   └── tailwind-config.js      # Tailwind theme config
│   │
│   ├── pages/                      # Public pages
│   │   ├── contact.html
│   │   ├── faq.html
│   │   ├── privacy-policy.html
│   │   └── errors/
│   │
│   └── uploads/
│       └── resumes/                # Resume storage
│
└── auth/                           # Shared authentication
    ├── login.html                  # Generic login
    └── signup.html                 # Generic signup
```

---

## 🔌 API Endpoints

### Student API (`/student/api/`)

| Endpoint | Method | Description | Auth Required |
|----------|--------|-------------|---------------|
| `auth.php` | POST | Student login/logout | No |
| `events.php` | GET | List events (with filters) | No |
| `event-details.php` | GET | Get event details | No |
| `event-registration.php` | POST | Register for event | Yes |
| `registrations.php` | GET | My registrations | Yes |
| `job-offers.php` | GET | List job offers | No |
| `job-detail.php` | GET | Job offer details | No |
| `job-applications.php` | POST | Submit application | Yes |
| `profile.php` | GET/PUT | Get/update profile | Yes |
| `calendar-events.php` | GET | Calendar sync data | Yes |

### Organization API (`/organization/api/`)

| Endpoint | Method | Description | Auth Required |
|----------|--------|-------------|---------------|
| `auth.php` | POST | Organization login/logout | No |
| `events.php` | GET/POST/PUT/DELETE | Manage events | Yes |
| `event-details.php` | GET | Event details | Yes |
| `registrations.php` | GET/PUT | View/manage registrations | Yes |
| `job-offers.php` | GET/POST | List/create job offers | Yes |
| `manage-job-offers.php` | PUT/DELETE | Update/delete job offers | Yes |
| `applications.php` | GET/PUT | View/update applications | Yes |
| `analytics.php` | GET | Analytics data | Yes |
| `dashboard.php` | GET | Dashboard statistics | Yes |
| `profile.php` | GET/PUT | Get/update profile | Yes |

### Admin API (`/admin/api/`)

| Endpoint | Method | Description | Auth Required |
|----------|--------|-------------|---------------|
| `adminlogin.php` | POST | Admin login | No |
| `dashboard_data.php` | GET | Dashboard statistics | Yes |
| `students.php` | GET/PUT | List/manage students | Yes |
| `organizations.php` | GET/PUT | List/manage organizations | Yes |
| `events.php` | GET/PUT/DELETE | Moderate events | Yes |
| `notifications.php` | GET/POST | Manage notifications | Yes |
| `gallery_photos.php` | GET/POST/DELETE | Manage gallery | Yes |
| `search.php` | GET | Global search | Yes |
| `admin_profile.php` | GET/PUT | Admin profile | Yes |

### Common Parameters

**Pagination:**
- `page`: Page number (default: 1)
- `per_page`: Items per page (default: varies by endpoint)

**Filtering:**
- `search`: Search query
- `category`: Event category filter
- `timeframe`: Time-based filter (upcoming/past/all)
- `status`: Status filter (active/inactive/pending)

**Response Format:**
All APIs return JSON with the following structure:
```json
{
  "success": true/false,
  "message": "Response message",
  "data": { /* Response data */ },
  "pagination": {
    "current_page": 1,
    "total_pages": 10,
    "total_items": 100
  }
}
```

---

## 📖 Usage Guide

### For Students

1. **Registration & Login**
   - Navigate to `/auth/signup.html`
   - Fill in your details and create an account
   - Login at `/student/auth/login.html`

2. **Browse Events**
   - View all events on the Events page
   - Filter by category, date, or search keywords
   - Click on an event to view details

3. **Register for Events**
   - Click "Register" on event details page
   - Some events require approval from organizers
   - Track your registrations in "My Registrations"

4. **Job Applications**
   - Browse job offers in the Job Opportunities section
   - Click "Apply" and upload your resume
   - Write a cover letter
   - Track applications in "My Applications"

### For Organizations

1. **Registration & Login**
   - Register at `/organization/auth/singup.html`
   - Wait for admin approval
   - Login at `/organization/auth/login.html`

2. **Create Events**
   - Go to Events → Create Event
   - Fill in event details (title, description, date, location)
   - Set capacity and approval requirements
   - Publish or save as draft

3. **Manage Registrations**
   - View registrations for each event
   - Approve/reject pending registrations
   - Export attendee lists

4. **Post Job Offers**
   - Go to Job Offers → Create New
   - Specify job details and requirements
   - Set job type (full-time, internship, etc.)
   - Publish the offer

5. **Review Applications**
   - View all applications in the Applications section
   - Review resumes and cover letters
   - Update application status (reviewed/shortlisted/rejected/accepted)

### For Administrators

1. **Login**
   - Access admin panel at `/admin/auth/admin-login.html`
   - Use admin credentials

2. **Manage Users**
   - Review and approve/reject student registrations
   - Review and approve/reject organization registrations
   - Activate/deactivate user accounts

3. **Moderate Events**
   - View all events across the platform
   - Edit or delete inappropriate events
   - Feature important events

4. **Gallery Management**
   - Upload platform-wide gallery images
   - Organize event photos
   - Delete inappropriate images

5. **Analytics & Reports**
   - View dashboard for platform statistics
   - Monitor user activity
   - Track event attendance trends

---

## 🤝 Contributing

We welcome contributions from the community! Here's how you can help:

### Reporting Issues

1. Check if the issue already exists
2. Create a new issue with:
   - Clear title and description
   - Steps to reproduce
   - Expected vs actual behavior
   - Screenshots (if applicable)

### Code Contributions

1. **Fork the repository**
   ```bash
   git clone https://github.com/0xkhyr/iteam-university-events-website.git
   ```

2. **Create a feature branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```

3. **Make your changes**
   - Follow existing code style
   - Comment your code
   - Test thoroughly

4. **Commit your changes**
   ```bash
   git commit -m "Add: Amazing new feature"
   ```

5. **Push to your fork**
   ```bash
   git push origin feature/amazing-feature
   ```

6. **Open a Pull Request**
   - Describe your changes
   - Reference any related issues

### Code Style Guidelines

- **PHP**: Follow PSR-12 coding standards
- **JavaScript**: Use ES6+ features, camelCase naming
- **HTML**: Semantic markup, proper indentation
- **CSS**: Use TailwindCSS utilities when possible
- **Comments**: Write clear, concise comments

---

## 📄 License

This project is licensed under the **MIT License**.

```
MIT License

Copyright (c) 2025 iTeam University

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## 📞 Contact & Support

### Project Maintainer
- **GitHub**: [@0xkhyr](https://github.com/0xkhyr)
- **Repository**: [iteam-university-events-website](https://github.com/0xkhyr/iteam-university-events-website)

### Support Channels

- 🐛 **Bug Reports**: [GitHub Issues](https://github.com/0xkhyr/iteam-university-events-website/issues)
- 💡 **Feature Requests**: [GitHub Discussions](https://github.com/0xkhyr/iteam-university-events-website/discussions)
- 📧 **Email**: support@iteamuniversity.com
- 📖 **Documentation**: [Wiki](https://github.com/0xkhyr/iteam-university-events-website/wiki)

### Community

- Join our developer community
- Share your feedback and suggestions
- Contribute to documentation
- Help other users

---

## 🙏 Acknowledgments

- Built with ❤️ for educational institutions
- TailwindCSS for the amazing utility-first framework
- PHP and MySQL communities
- All contributors and testers

---

<div align="center">

**[⬆ Back to Top](#iteam-university-event-management-platform)**

Made with ❤️ by [@0xkhyr](https://github.com/0xkhyr)

</div>
