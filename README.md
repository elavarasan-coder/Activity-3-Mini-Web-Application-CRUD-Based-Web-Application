🌌 VSBEC EVENTVERSE
College Event Registration Portal
V.S.B. Engineering College, Karur (VSBEC)
Connect • Create • Participate • Celebrate
Design Identity: VSBEC EventVerse – Aurora Luxe
Table of Contents
Project Overview
Problem Statement
Project Objectives
Key Features
User Roles
Technology Stack
System Architecture
Application Modules
Event Management
Student Management
Registration Management
Digital Event Pass
Notification System
Dashboard and Analytics
Search and Filtering
Validation and Security
Database Design
Database Tables
Table Relationships
Frontend Structure
Backend Structure
REST API Endpoints
Folder Structure
Installation Requirements
MySQL Database Setup
Backend Installation
Frontend Installation
Environment Configuration
Running the Project
Sample Login Credentials
Sample Data
Project Demonstration Steps
CRUD Operations Explanation
Validation Rules
Responsive Design
Aurora Luxe Design System
Future Enhancements
Advantages
Limitations
Learning Outcomes
Project Demonstration Script (Viva Guide)
Conclusion
Developer Information
1. Project Overview
VSBEC EVENTVERSE is a premium, full-stack college event registration and management platform built specifically for V.S.B. Engineering College, Karur.
The platform gives the college's administration a single place to:
Create and manage college events
Maintain a complete database of student records
Manage and track event registrations
Approve or reject student registrations
Automatically generate digital event passes with QR codes
Send notifications to users
Monitor event participation through visual analytics
This is not a static prototype or a design mock-up. It is a complete CRUD-based (Create, Read, Update, Delete) full-stack web application, with a real database, a working backend API, and a fully functional frontend. Every button, form, and table in the application is connected to real data operations, exactly like a production-grade system — just scoped appropriately for a college mini-project.
2. Problem Statement
In most colleges, event management is still handled manually or through scattered tools:
Event details are shared through WhatsApp, notice boards, or word of mouth.
Student registrations are collected on paper or in random Excel sheets.
There is no way to check event capacity in real time, leading to overcrowding.
Duplicate registrations from the same student are common and hard to catch manually.
Verifying whether a student is genuinely registered for an event (at the entrance) is slow and error-prone.
There is no central dashboard to see how many students registered, which events are popular, or which departments are most active.
VSBEC EVENTVERSE solves this by digitizing the entire event lifecycle — from event creation to registration, approval, digital pass generation, and analytics — in one secure, easy-to-use web portal.
3. Project Objectives
To build a centralized digital platform for managing college events.
To allow administrators to create, update, and manage events and student data efficiently.
To automate the registration process while preventing duplicate or invalid entries.
To generate a verifiable digital event pass with a QR code for every successful registration.
To provide real-time notifications and analytics for better decision-making.
To apply full-stack web development concepts (React + Django + MySQL) in a real, working project.
To design a visually premium and responsive interface using the Aurora Luxe design system.
4. Key Features
Admin Features
Feature
Description
Login
Secure token-based login for the administrator
Dashboard
Overview of events, students, and registrations
Event CRUD
Create, view, edit, and delete events
Student CRUD
Create, view, edit, and delete student records
Registration Management
View all registrations in one place
Approve Registration
Confirm a student's seat for an event
Reject Registration
Decline a registration with reason tracking
Delete Registration
Remove an invalid or cancelled registration
Search
Quickly find events, students, or registrations
Filtering
Filter records by status, category, or department
Analytics
Visual charts showing participation trends
Notifications
View system-generated alerts
Profile
View and manage admin profile details
Dark/Light Theme
Switch between Aurora dark mode and Ivory light mode
Logout
Securely end the session
Student-Facing Features
Feature
Description
Explore Events
Browse all upcoming and ongoing events
Register for Events
Submit a registration for a chosen event
View Registrations
See all events registered for
Check Registration Status
Track whether a registration is pending, approved, or rejected
View Event Pass
Access the digital event pass once approved
QR Code
View the unique QR code linked to the registration
Notifications
Receive updates about registration status
Profile
View personal and academic details
5. User Roles
The system supports two primary roles:
Role
Access Level
Administrator
Full access — manage events, students, registrations, notifications, and analytics
Student
Limited access — browse events, register, view own registrations and event pass
Each role has a different dashboard and different permissions enforced at the API level, so a student can never access another student's data or perform admin-only actions.
6. Technology Stack
Frontend
Technology
Purpose (Explained Simply)
React
Used to build the user interface as reusable components (like buttons, cards, forms) instead of writing repetitive HTML. Makes the app fast and interactive.
HTML
The basic skeleton/structure of every web page.
CSS
Used to style the pages — colors, spacing, layout, animations (the Aurora Luxe theme is built using CSS).
JavaScript
The programming language that makes the webpage interactive — handling clicks, form submissions, and API calls.
Vite
A fast build tool that runs the React app during development and bundles it for production. It makes the app start almost instantly compared to older tools.
Backend
Technology
Purpose (Explained Simply)
Python
The programming language used to write the server-side logic.
Django
A Python web framework that provides a ready-made structure for building the backend — handling URLs, database models, and admin tools, so we don't build everything from scratch.
Django REST Framework (DRF)
A toolkit built on top of Django that helps us turn our data into a REST API (JSON responses) that the React frontend can talk to.
Database
Technology
Purpose (Explained Simply)
MySQL
A relational database used to permanently store all data — students, events, registrations, passes, and notifications — in organized tables.
Authentication
Technology
Purpose (Explained Simply)
DRF Token Authentication
When a user logs in, the server gives them a unique "token" (like a digital key). This token is sent with every future request to prove who the user is, instead of sending username/password again and again.
Other Tools
Technology
Purpose (Explained Simply)
QR Code Generation
Used to create a scannable QR code for each registration, which is embedded in the digital event pass.
Recharts
A charting library used in the React dashboard to display analytics (like bar charts and pie charts) in a simple visual way.
7. System Architecture
VSBEC EVENTVERSE follows a 3-tier client-server architecture:
flowchart LR
    A[React Frontend<br/>Vite + JS] -- REST API calls / JSON --> B[Django REST Framework<br/>Backend Server]
    B -- ORM Queries --> C[(MySQL Database)]
    B -- Token Auth --> A
    B -- QR Code Generation --> A
How it works, in simple terms:
The React frontend (running in the browser) sends requests to the backend whenever a user clicks something — like "Register for Event."
The Django REST Framework backend receives the request, checks if the user is authenticated, processes the business logic (like checking seat availability), and talks to the database.
MySQL stores and returns the actual data.
The backend sends a response back as JSON, and React updates the screen without reloading the page.
8. Application Modules
The application is organized into these functional modules:
Authentication Module – Login, token generation, session handling
Event Module – Event CRUD, status management
Student Module – Student CRUD, academic details
Registration Module – Registration workflow, approval/rejection
Event Pass Module – Digital pass and QR code generation
Notification Module – System alerts and read/unread tracking
Dashboard Module – Statistics and analytics visualization
9. Event Management
Every event stored in the system has the following fields:
Field
Description
Event ID
Unique identifier (auto-generated)
Event Name
Title of the event
Category
Type of event (Technical, Cultural, Sports, Workshop, etc.)
Description
Detailed information about the event
Date
Date on which the event is held
Start Time
Event start time
End Time
Event end time
Venue
Location of the event
Organizer
Name of the person/club/department organizing it
Department
Department associated with the event
Maximum Participants
Seat limit for the event
Registration Deadline
Last date/time to register
Event Status
Current status of the event
Event Image
Poster/banner image for the event
Event Status Values
Status
Meaning
UPCOMING
Event has not started yet, registrations are open (if before deadline)
ONGOING
Event is currently happening
COMPLETED
Event has finished
CANCELLED
Event has been cancelled by the admin
CRUD Operations on Events
Create – Admin fills a form with all event details and submits it; a new event record is created.
Read – Events are listed on the Explore Events page (students) and Event Management page (admin); a single event can be viewed in detail.
Update – Admin can edit any field of an existing event (e.g., change venue or extend deadline).
Delete – Admin can remove an event that is no longer needed (e.g., created by mistake).
10. Student Management
Admins maintain a full digital record of students who use the system. Typical fields include:
Student Name
Register Number
Department
Year/Class
Email
Phone Number
CRUD Operations on Students
Create – Admin adds a new student record.
Read – Admin views the full list of students, or searches for a specific one.
Update – Admin edits a student's details (e.g., corrects a phone number).
Delete – Admin removes a student record that is no longer valid.
11. Registration Management
Registration Workflow
flowchart TD
    A[Student selects an event] --> B[Student details are selected/entered]
    B --> C{Validation Passed?}
    C -- No --> C1[Show error message]
    C -- Yes --> D{Duplicate Registration?}
    D -- Yes --> D1[Registration blocked]
    D -- No --> E{Deadline Passed?}
    E -- Yes --> E1[Registration blocked]
    E -- No --> F{Seats Available?}
    F -- No --> F1[Registration blocked - Event Full]
    F -- Yes --> G[Registration Created]
    G --> H[Unique Registration ID Generated]
    H --> I[Digital Event Pass Generated]
    I --> J[QR Code Generated]
    J --> K[Notification Created]
Step-by-step explanation:
The student picks an event they are interested in.
Their student details are selected (if already an existing record) or entered.
The system checks basic validation (required fields, correct format).
The system checks whether this student has already registered for the same event.
The system checks whether the registration deadline has passed.
The system checks whether there are available seats left (current registrations vs. Maximum Participants).
If all checks pass, a new registration record is created.
A unique Registration ID is generated for tracking.
A Digital Event Pass is generated automatically.
A QR Code is generated and linked to the pass.
A notification is created to inform the student of their registration status.
Duplicate Registration Prevention
Duplicate registrations are prevented at two levels, for extra safety:
Backend Validation – Before saving, the Django view checks if a registration already exists for the same (student, event) pair.
Database Unique Constraint – The Registrations table has a unique constraint on the combination of student_id and event_id, so even if the backend check is somehow bypassed, MySQL itself will reject the duplicate entry.
This "defense in depth" approach ensures data integrity is never compromised.
Registration Statuses
Status
Meaning
PENDING
Registration submitted, awaiting admin review
APPROVED
Admin has confirmed the student's seat
REJECTED
Admin has declined the registration
12. Digital Event Pass
Once a registration is approved, the system automatically generates a Digital Event Pass containing:
VSBEC EVENTVERSE (branding)
V.S.B. Engineering College, Karur
Student Name
Register Number
Department
Event Name
Date
Time
Venue
Registration ID
QR Code
Purpose of the QR Code
The QR code embeds the Registration ID. At the event entrance, this code can be scanned (manually verified by looking up the Registration ID) to instantly confirm that the student is a genuine, approved participant — eliminating the need for paper lists or manual name searches.
Print / Save as PDF
The digital event pass page includes a Print option. Using the browser's built-in print dialog, the student (or admin) can either:
Print a physical copy of the pass, or
Choose "Save as PDF" as the print destination to download a digital copy.
This requires no extra library — it uses the browser's native print functionality, styled specifically for a clean printed layout.
13. Notification System
The system automatically creates notifications for key events, such as:
A registration is approved
A registration is rejected
An event is updated or cancelled
Each notification has a read/unread status, and users can mark notifications as read once viewed. This keeps students and admins informed without needing to constantly check the system manually.
14. Dashboard and Analytics
The admin dashboard provides a real-time visual summary of the platform's activity, including:
Total number of events (and breakdown by status)
Total number of registered students
Total number of registrations (pending/approved/rejected)
Most popular events (by registration count)
Department-wise participation
These are visualized using Recharts, with bar charts and pie/donut charts, making it easy to understand trends at a glance instead of reading raw numbers.
15. Search and Filtering
To make managing large amounts of data easy, the system supports:
Search – Find events, students, or registrations by typing a name, register number, or keyword.
Filtering – Narrow down lists using criteria such as:
Event category
Event status (Upcoming/Ongoing/Completed/Cancelled)
Department
Registration status (Pending/Approved/Rejected)
This makes the admin's job much faster, especially as the number of events and students grows.
16. Validation and Security
All form inputs are validated on both the frontend (for immediate feedback) and backend (for actual security).
Authentication is required for all protected API endpoints using DRF Token Authentication.
Sensitive actions (approve/reject/delete) are restricted to admin users only.
Passwords are never stored in plain text — Django's built-in password hashing is used.
API errors are handled gracefully and return clear, structured error messages instead of raw server errors.
(Detailed validation rules are covered in Section 34.)
17. Database Design
The database is designed using standard relational database principles:
Every table has a Primary Key to uniquely identify each row.
Related tables are connected using Foreign Keys.
Unique constraints prevent duplicate or invalid data (e.g., duplicate registrations).
The schema is normalized to avoid unnecessary data repetition.
18. Database Tables
AdminProfile
Column
Type
Description
id
Primary Key
Unique ID
user_id
Foreign Key → User
Linked Django user account
full_name
Varchar
Admin's full name
phone
Varchar
Contact number
role
Varchar
e.g., Event Administrator
Students
Column
Type
Description
id
Primary Key
Unique student record ID
name
Varchar
Student's full name
register_number
Varchar (Unique)
College register number
department
Varchar
Department name
year
Varchar
Current year/class
email
Varchar
Email address
phone
Varchar
Contact number
Events
Column
Type
Description
id
Primary Key
Unique event ID
name
Varchar
Event name
category
Varchar
Event category
description
Text
Full description
date
Date
Event date
start_time
Time
Start time
end_time
Time
End time
venue
Varchar
Venue
organizer
Varchar
Organizer name
department
Varchar
Associated department
max_participants
Integer
Seat limit
registration_deadline
DateTime
Last date/time to register
status
Varchar
UPCOMING / ONGOING / COMPLETED / CANCELLED
image
Image field
Event banner/poster
Registrations
Column
Type
Description
id
Primary Key
Unique registration ID
student_id
Foreign Key → Students
Registered student
event_id
Foreign Key → Events
Event registered for
status
Varchar
PENDING / APPROVED / REJECTED
registered_at
DateTime
Timestamp of registration
(unique constraint)
student_id + event_id
Prevents duplicate registrations
EventPass
Column
Type
Description
id
Primary Key
Unique pass ID
registration_id
Foreign Key → Registrations
Linked registration
qr_code
Image/Text field
QR code data/image
issued_at
DateTime
When the pass was generated
Notifications
Column
Type
Description
id
Primary Key
Unique notification ID
user_id
Foreign Key → User
Recipient of the notification
message
Text
Notification content
is_read
Boolean
Read/unread status
created_at
DateTime
Timestamp
19. Table Relationships
erDiagram
    USER ||--o| ADMINPROFILE : has
    USER ||--o{ NOTIFICATION : receives
    STUDENTS ||--o{ REGISTRATIONS : makes
    EVENTS ||--o{ REGISTRATIONS : receives
    REGISTRATIONS ||--|| EVENTPASS : generates

    ADMINPROFILE {
        int id PK
        int user_id FK
        string full_name
        string phone
        string role
    }
    STUDENTS {
        int id PK
        string name
        string register_number
        string department
        string year
    }
    EVENTS {
        int id PK
        string name
        string category
        date date
        int max_participants
        string status
    }
    REGISTRATIONS {
        int id PK
        int student_id FK
        int event_id FK
        string status
        datetime registered_at
    }
    EVENTPASS {
        int id PK
        int registration_id FK
        string qr_code
    }
    NOTIFICATION {
        int id PK
        int user_id FK
        string message
        bool is_read
    }
In simple words:
One User account has one AdminProfile (for admins).
One Student can make many Registrations (for different events).
One Event can have many Registrations (from different students).
Each Registration generates exactly one EventPass.
A User can receive many Notifications.
20. Frontend Structure
The React frontend is organized into reusable components and pages:
Pages – Login, Dashboard, Events, Students, Registrations, Event Pass, Notifications, Profile
Components – Navbar, Sidebar, Cards, Tables, Modals, Forms, Charts
API Layer (api.js) – Centralized file that handles all HTTP requests to the Django backend
Styles (styles.css) – Implements the Aurora Luxe design system (colors, glassmorphism, gradients)
Theme Handling – Manages switching between Dark (Aurora) mode and Light (Ivory) mode
21. Backend Structure
The Django backend follows the standard Django project layout:
config/ – Project-level settings, main URL routing, and WSGI entry point
events/ – The core Django app containing:
models.py – Defines all database tables (Students, Events, Registrations, etc.)
serializers.py – Converts database objects into JSON (and validates incoming JSON)
views.py – Contains the logic for each API endpoint (business logic)
urls.py – Maps URL paths to their corresponding views
admin.py – Registers models with Django's built-in admin panel
management/ – Custom management commands (e.g., seed_data for sample data)
22. REST API Endpoints
Authentication & General
Method
Endpoint
Purpose
POST
/api/login/
Authenticates a user and returns an auth token
GET
/api/me/
Returns the currently logged-in user's profile details
GET
/api/dashboard/
Returns summary statistics for the dashboard
Students
Method
Endpoint
Purpose
GET
/api/students/
Lists all students
POST
/api/students/
Creates a new student record
GET
/api/students/{id}/
Retrieves details of a specific student
PUT
/api/students/{id}/
Updates a specific student's details
DELETE
/api/students/{id}/
Deletes a specific student record
Events
Method
Endpoint
Purpose
GET
/api/events/
Lists all events
POST
/api/events/
Creates a new event
GET
/api/events/{id}/
Retrieves details of a specific event
PUT
/api/events/{id}/
Updates a specific event's details
DELETE
/api/events/{id}/
Deletes a specific event
Registrations
Method
Endpoint
Purpose
GET
/api/registrations/
Lists all registrations (admin view)
POST
/api/registrations/
Creates a new registration
GET
/api/registrations/{id}/
Retrieves details of a specific registration
DELETE
/api/registrations/{id}/
Deletes a registration
POST
/api/registrations/{id}/approve/
Approves a pending registration
POST
/api/registrations/{id}/reject/
Rejects a pending registration
GET
/api/registrations/mine/
Returns registrations belonging to the logged-in student
Event Pass
Method
Endpoint
Purpose
GET
/api/passes/
Retrieves digital event pass(es), including QR code data
Notifications
Method
Endpoint
Purpose
GET
/api/notifications/
Lists all notifications for the logged-in user
POST
/api/notifications/{id}/mark_read/
Marks a specific notification as read
23. Folder Structure
VSBEC_EVENTVERSE/
│
├── README.md
│
├── backend/
│   ├── manage.py
│   ├── requirements.txt
│   ├── .env.example
│   │
│   ├── config/
│   │   ├── settings.py
│   │   ├── urls.py
│   │   └── wsgi.py
│   │
│   └── events/
│       ├── models.py
│       ├── serializers.py
│       ├── views.py
│       ├── urls.py
│       ├── admin.py
│       └── management/
│           └── commands/
│               └── seed_data.py
│
└── frontend/
    ├── package.json
    ├── index.html
    └── src/
        ├── main.jsx
        ├── api.js
        └── styles.css
24. Installation Requirements
Before setting up the project, make sure the following are installed on your system:
Requirement
Recommended Version
Python
3.10 or above
Node.js
18.x or above
npm
Comes bundled with Node.js
MySQL Server
8.0 or above
pip
Comes bundled with Python
Git (optional)
Latest version, for cloning the repository
25. MySQL Database Setup
Open your MySQL client (MySQL Workbench, terminal, or phpMyAdmin).
Create a new database for the project:
CREATE DATABASE vsbec_eventverse;
Make sure you have a MySQL user with permission to access this database. (You can use your existing root user for a college mini-project setup.)
26. Backend Installation
Open a terminal and navigate to the backend folder:
cd backend
Create a virtual environment:
python -m venv venv
Activate the virtual environment:
Windows:
venv\Scripts\activate
macOS/Linux:
source venv/bin/activate
Install the required Python packages:
pip install -r requirements.txt
Apply database migrations:
python manage.py makemigrations
python manage.py migrate
Load sample data (optional but recommended for demonstration):
python manage.py seed_data
Start the backend development server:
python manage.py runserver
27. Frontend Installation
Open a new terminal window (keep the backend running) and navigate to the frontend folder:
cd frontend
Install the required npm packages:
npm install
Start the frontend development server:
npm run dev
28. Environment Configuration
Create a .env file inside the backend/ folder (based on .env.example) with your local MySQL details:
# Django Settings
SECRET_KEY=your-secret-key-here
DEBUG=True

# MySQL Database Settings
DB_NAME=vsbec_eventverse
DB_USER=root
DB_PASSWORD=your_mysql_password
DB_HOST=localhost
DB_PORT=3306
⚠️ Important: Never commit your actual .env file (with real passwords) to a public repository. Only .env.example (with placeholder values) should be shared.
29. Running the Project
Once both servers are running:
Service
URL
Frontend (React + Vite)
http://localhost:5173
Backend (Django REST API)
http://127.0.0.1:8000
Open http://localhost:5173 in your browser to access the VSBEC EventVerse portal. The React app will automatically communicate with the Django backend running at port 8000.
30. Sample Login Credentials
For demonstration and evaluation purposes, use the following admin login:
Field
Value
Register Number
922525106091
Password
EventVerse@123
⚠️ Note: These are demo credentials only, meant for project evaluation/demonstration. In any real-world/production deployment, these must be changed immediately and never reused.
31. Sample Data
Running python manage.py seed_data populates the database with sample records, including:
A default admin profile
A few sample students across different departments
A few sample events (Technical, Cultural, Workshop categories) with different statuses
A few sample registrations in different states (Pending/Approved/Rejected)
This allows the entire application to be demonstrated immediately without manually creating data first.
32. Project Demonstration Steps
Follow this sequence for a smooth live demonstration:
Start the MySQL server.
Start the Django backend server (python manage.py runserver).
Start the React frontend (npm run dev).
Open the login page in the browser.
Log in using the demo credentials.
Show the premium home page.
Open the Dashboard.
Show the statistics and charts.
Open the Events section.
Create a new event.
Edit an existing event.
Demonstrate search/filter on events.
Open the Students section.
Add a new student.
Edit a student's details.
Search for a student.
Open the Registrations section.
Register a student for an event.
Attempt the same registration again to show duplicate prevention.
Approve a pending registration.
Show the automatically generated digital event pass.
Show the QR code on the pass.
Print (or Save as PDF) the event pass.
Open the Notifications section.
Show the analytics/dashboard charts again with updated data.
Open the Profile page.
Toggle between Dark and Light themes.
Log out.
33. CRUD Operations Explanation
CRUD stands for the four basic operations every data-driven application performs:
Operation
Meaning
Example
Create
Add a new record
Adding a new event, a new student, or a new registration
Read
View existing records
Viewing the list of all events or a single student's profile
Update
Edit an existing record
Changing an event's venue, or correcting a student's phone number
Delete
Remove a record
Deleting a cancelled event, or removing a duplicate student entry
CRUD Examples in This Project
Students:
Create → Admin adds "Priya S, ECE, 2nd Year"
Read → Admin views the full student list
Update → Admin corrects Priya's phone number
Delete → Admin removes a student who left the college
Events:
Create → Admin adds "Tech Symposium 2026"
Read → Students browse this event on the Explore Events page
Update → Admin changes the venue from Seminar Hall to Auditorium
Delete → Admin removes an event that was cancelled
Registrations:
Create → A student registers for "Tech Symposium 2026"
Read → Admin views all registrations for that event
Update → (Handled via Approve/Reject actions, changing status)
Delete → Admin removes an invalid registration
34. Validation Rules
Rule
Description
Required Fields
All mandatory fields must be filled before submission
Email Validation
Email must follow a valid format (e.g., name@domain.com)
Phone Validation
Phone number must be exactly 10 digits
Register Number Validation
Must follow the college's register number format and be unique
Duplicate Registration Prevention
A student cannot register for the same event twice (checked at backend + database level)
Event Capacity Checking
Registration is blocked once Maximum Participants is reached
Registration Deadline Checking
Registration is blocked after the Registration Deadline has passed
Event Status Checking
Registrations are only allowed for events that are UPCOMING (not CANCELLED or COMPLETED)
Date/Time Validation
Event end time must be after the start time; dates must be valid
Authentication
All protected routes require a valid auth token
API Error Handling
Errors return clear JSON messages with appropriate HTTP status codes (400, 401, 403, 404, etc.)
35. Responsive Design
VSBEC EventVerse is built to work smoothly across devices:
Desktop – Full dashboard layout with sidebars and multi-column grids
Tablet – Adjusted grid layouts and collapsible navigation
Mobile – Single-column stacked layout, touch-friendly buttons, and a simplified navigation menu
This is achieved using CSS Flexbox/Grid and media queries, ensuring the Aurora Luxe theme looks premium on any screen size.
36. Aurora Luxe Design System
The entire interface follows a custom design language called Aurora Luxe, inspired by aurora skies and modern luxury dashboards.
Color Palette
Color Name
Hex Code
Sample
Midnight Navy
#0B1026
Primary dark background
Deep Purple
#21113D
Secondary dark background
Electric Violet
#7C3AED
Primary accent / buttons
Aurora Magenta
#C026D3
Gradient accent / highlights
Champagne Gold
#F4D06F
Premium highlights / badges
Ivory White
#FFFDF7
Light mode background
Soft Lavender
#EDE9FE
Light mode surface/cards
Visual Design Principles
Glassmorphism – Semi-transparent, blurred card backgrounds for a modern "frosted glass" look
Aurora Gradients – Smooth gradients blending Electric Violet and Aurora Magenta, inspired by the northern lights
Frosted Glass Cards – Cards with subtle blur and transparency effects
Glowing Borders – Soft glow effects around key interactive elements
Soft Shadows – Gentle drop shadows for depth without harshness
Rounded Corners – Consistent, modern rounded edges on cards, buttons, and inputs
Modern Typography – Clean, legible fonts with clear hierarchy (headings vs. body text)
Minimal Geometric Patterns – Subtle background patterns that don't distract from content
Subtle Animations – Smooth hover effects and transitions (no jarring movements)
Responsive Layout – Adapts gracefully to all screen sizes
Dark Mode – The default "Aurora" theme using Midnight Navy and Deep Purple tones
Ivory Light Mode – An alternate light theme using Ivory White and Soft Lavender tones
37. Future Enhancements
Student self-registration/login (currently managed by admin)
Google/Microsoft college account login (SSO)
Email notifications for registration updates
SMS notifications for critical alerts
Push notifications (browser/mobile)
Dedicated QR scanner module for event-day entry verification
Automatic certificate generation for participants
Attendance tracking linked to QR scans
Post-event feedback collection from students
Faculty/organizer-level accounts with limited admin access
Cloud deployment (e.g., hosting backend and frontend on cloud platforms)
Advanced analytics (trends over semesters, department comparisons)
AI-based event recommendations based on student interests
38. Advantages
Centralized management of all college events in one platform
Simple and quick student registration process
Significantly reduced manual paperwork and effort
Reliable duplicate registration prevention
Real-time seat availability checking
Professional digital event pass for every participant
QR-based identification for fast, reliable verification
Powerful search and filtering for large datasets
Visual analytics for better event planning decisions
Fully responsive design that works on any device
Overall improved and modern campus event experience
39. Limitations
Requires proper internet/network connectivity when deployed beyond localhost
MySQL server must be correctly installed and configured before use
Current authentication system is designed appropriately for a college mini-project scope, not enterprise-scale production
QR code verification is currently visual/manual; it can be expanded into a dedicated scanning module using a camera-based scanner
Email/SMS integration is not yet included but can be added as a future enhancement
40. Learning Outcomes
Through building VSBEC EventVerse, a 2nd-year ECE student gains hands-on experience in:
React basics – Components, props, state, and hooks
HTML & CSS – Structuring and styling modern web pages
JavaScript – DOM manipulation, event handling, async operations
Python – Core programming concepts applied to real backend logic
Django – Building a structured backend using models, views, and URLs
REST APIs – Designing and consuming APIs between frontend and backend
MySQL – Designing relational database schemas
CRUD Operations – Implementing Create, Read, Update, Delete across a real application
Authentication – Understanding token-based login systems
Database Relationships – Working with primary keys, foreign keys, and constraints
Form Validation – Implementing both client-side and server-side checks
Responsive Design – Building interfaces that adapt to different screen sizes
API Integration – Connecting a React frontend to a Django backend over HTTP
Project Structure – Organizing a full-stack project professionally
Software Development Workflow – Following a real development lifecycle from setup to demonstration
41. Project Demonstration Script (Viva Guide)
A simple, spoken-language script that ELAVARASAN R can use during the project viva/demonstration.
What is the project? "VSBEC EventVerse is a web-based event registration portal built for our college, V.S.B. Engineering College, Karur. It allows the admin to create events, manage students, and handle registrations, while automatically generating a digital event pass with a QR code for every approved participant."
What problem does it solve? "In colleges, event registration is usually done manually — using paper forms or WhatsApp messages. This causes duplicate entries, overcrowding, and confusion at the entrance. My project solves this by digitizing the whole process, from registration to verification."
Why did we use React? "React lets us build the user interface using small, reusable components like buttons and cards. This makes the app faster to build, easier to maintain, and gives users a smooth, app-like experience without reloading the page every time."
Why did we use Django? "Django is a Python web framework that comes with a lot of built-in tools, like an admin panel and database handling. It let us focus on our project's logic instead of building basic server features from scratch. We used Django REST Framework specifically to turn our data into an API that React can use."
Why did we use MySQL? "MySQL is a reliable, widely-used relational database. It lets us store our data — students, events, registrations — in organized tables and define relationships between them, like linking a registration to both a student and an event."
What is CRUD? "CRUD stands for Create, Read, Update, and Delete. These are the four basic operations we perform on our data — for example, creating a new event, reading the list of students, updating a registration's status, or deleting an old record."
How does registration work? "A student selects an event and submits their details. The system checks if all fields are valid, whether they've already registered for that event, whether the deadline has passed, and whether seats are still available. If everything is fine, the registration is created, and a digital event pass with a QR code is generated automatically."
How is duplicate registration prevented? "We prevent duplicates in two ways. First, our backend code checks if a registration already exists for that student and event before creating a new one. Second, our database itself has a unique constraint on the student-event combination, so even if something slips through the code, the database will reject it."
What is the digital event pass? "It's an automatically generated pass that contains the student's name, register number, department, and the event details, along with a QR code. It acts as proof that the student is registered and approved for that event."
What is the purpose of the QR code? "The QR code contains the registration ID. At the event, this can be scanned or checked to instantly confirm that the person is a genuine, approved participant, instead of manually searching through a paper list."
What are the future enhancements? "In the future, we plan to add student self-login, email and SMS notifications, a dedicated QR scanner for entry verification, certificate generation, attendance tracking, and cloud deployment so the platform can be used college-wide."
42. Conclusion
VSBEC EVENTVERSE successfully demonstrates how a full-stack web application — built with React, Django, and MySQL — can solve a real, everyday problem faced by colleges: managing events and registrations efficiently.
By combining a clean, modern Aurora Luxe design with solid backend logic, secure authentication, and thoughtful validation (like duplicate registration prevention and seat-limit checks), this project goes beyond a basic academic exercise and reflects the structure of a real-world production application.
Beyond the technical implementation, this project provided practical, hands-on experience in full-stack development, database design, API design, and UI/UX thinking — skills directly relevant to a career in software engineering and electronics-adjacent computing fields.
43. Developer Information
�

🌌 VSBEC EVENTVERSE
College Event Registration Portal
V.S.B. Engineering College, Karur
Developed by ELAVARASAN R
Field
Details
Register Number
922525106091
Class
2nd Year
Department
ECE (Electronics and Communication Engineering)
Role
Event Administrator
Contact
7397112875
Connect • Create • Participate • Celebrate
�
