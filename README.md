readme = r'''# Construct360

<u>Workforce Management System</u>

Construct360 is a workforce management system developed by **Constant Technology** for **ROCLA (Pty) Ltd**. It is designed to help an organisation manage important day-to-day workforce activities through a centralised digital system instead of relying on paper-based processes and manual communication.

The system brings together employee attendance, daily productivity recording, leave applications, workplace notifications and user administration. It consists of a mobile application for Employees and Supervisors, an administrator web application, a central backend and a shared database.

![Construct360 application icon](assets/construct360-app-icon.png)

---

## Table of Contents

- [About Construct360](#about-construct360)
- [The Problem Construct360 Addresses](#the-problem-construct360-addresses)
- [The Proposed Solution](#the-proposed-solution)
- [System Components](#system-components)
- [User Roles](#user-roles)
- [Main Features](#main-features)
  - [Attendance Management](#attendance-management)
  - [Productivity Management](#productivity-management)
  - [Leave Management](#leave-management)
  - [Notifications and Communication](#notifications-and-communication)
  - [Administrator Web Application](#administrator-web-application)
  - [Registration and Access Control](#registration-and-access-control)
- [How the System Works](#how-the-system-works)
- [Security and Access Management](#security-and-access-management)
- [Current Limitations and Planned Improvements](#current-limitations-and-planned-improvements)
- [Benefits of Construct360](#benefits-of-construct360)
- [Project Information](#project-information)

---

## About Construct360

Construct360 is intended to make workforce administration more organised, accessible and efficient. It provides different tools for employees, supervisors and administrators, with each role receiving access to the functions relevant to its responsibilities.

Employees use the mobile application to view their personal attendance information, present their QR identification code for attendance recording, submit leave applications and receive workplace notifications.

Supervisors use the mobile application to record attendance by scanning employee QR codes, record planned and actual daily production, review and process departmental leave requests, and communicate with employees.

Administrators use the web application to manage registration requests, user accounts, system roles and account access. They can also view available login activity logs.

All these activities are supported by a shared backend and central database. This allows information submitted through the mobile application and administrator website to be processed and stored in one central system.

## The Problem Construct360 Addresses

Many workforce activities can become time-consuming when they depend on physical documents, manual registers and communication between several people.

The project documentation identifies a number of processes that Construct360 is intended to improve:

### 1. Manual attendance recording

Traditional attendance registers require attendance information to be captured and managed manually. This can make it harder to maintain consistent records and quickly retrieve an employee's attendance history.

### 2. Paper-based leave applications

In the process observed by the development team, an employee had to collect a physical leave form from reception, complete it and return it. Reception then had to send the form to the relevant supervisor. After a decision was made, the form had to return to reception, which would contact the employee by email or SMS.

The documented process could take approximately one week from application to communication of the outcome. It also involved several handovers and administrative steps.

### 3. Limited visibility of daily production

Supervisors need a way to compare planned production with the actual production achieved during a working day. Without a central record, reviewing whether a daily target was met can require additional manual tracking.

### 4. Workplace communication

Important workplace announcements and departmental updates need to reach the relevant employees. Relying on separate communication methods can make it more difficult to keep information in one accessible place.

### 5. User and access administration

An organisation needs to manage who can use its workforce system and what information each person is allowed to access. Employees, supervisors and administrators have different responsibilities and should not all have the same permissions.

## The Proposed Solution

Construct360 brings these workforce activities into one digital environment.

Instead of using physical attendance registers, supervisors scan employee QR codes through the mobile application. Instead of passing paper leave forms between reception and supervisors, employees submit requests through the app and supervisors process them there. Supervisors can also record planned and actual production, while notifications provide a central way to communicate workplace information.

The administrator website provides a separate place to manage accounts, registration requests, roles and access. A central backend validates requests, applies the system's business rules and communicates with the database.

The aim is to reduce paperwork, simplify administrative processes, improve access to workforce information and make routine workforce activities easier to manage.

---

## System Components

Construct360 is made up of four main system components.

| Component | Purpose |
|---|---|
| Mobile application | Used by Employees and Supervisors for workforce activities. |
| Administrator web application | Used by Administrators to manage users, registration requests, roles and account access. |
| Backend | Processes requests, applies business rules, validates information and enforces permissions. |
| Central database | Stores user accounts, attendance, productivity, leave, notifications and available login records. |

### Mobile Application

The mobile application is the main working interface for Employees and Supervisors. The functions displayed depend on the user's assigned role.

![Employee dashboard](assets/employee-dashboard.png)

*Employee mobile dashboard.*

![Supervisor dashboard](assets/supervisor-dashboard.png)

*Supervisor mobile dashboard.*

### Administrator Web Application

The administrator website is a separate interface for managing the system. It provides account administration and access-control functions.

![Administrator dashboard](assets/admin-dashboard.png)

*Administrator dashboard overview.*

### Backend and Central Database

The backend connects the two applications to the central database. It is responsible for processing information, validating operations and ensuring that users can only perform actions allowed by their assigned roles.

The database stores the main information required by the system, including:

- User account details and assigned roles.
- Employee attendance records and timestamps.
- Planned and accumulated productivity figures.
- Leave applications and their statuses.
- Notifications and related information.
- Available account login activity logs.

---

## User Roles

Construct360 has three primary user roles: **Administrator**, **Supervisor** and **Employee**.

| User Role | Application | Main Responsibilities |
|---|---|---|
| Administrator | Web application | Manages registration requests, user accounts, roles and account access. |
| Supervisor | Mobile application | Manages departmental attendance, productivity records, leave requests and employee notifications. |
| Employee | Mobile application | Views personal attendance, presents a QR code, submits leave applications and receives notifications. |

### Administrator

The Administrator is responsible for managing access to Construct360. The administrator web application allows an authorised Administrator to:

- View incoming registration requests.
- Approve or decline registration requests.
- Assign user roles, including Employee, Supervisor and Administrator.
- Search for users by name or identification details.
- View user account information.
- Block accounts to restrict access and unblock accounts when access should be restored.
- View available login logs.

Only an authorised Administrator should be able to grant or change elevated system roles.

### Supervisor

A Supervisor is responsible for employees within an assigned department. The Supervisor uses the mobile application to:

- Scan employee QR codes to record clock-in and clock-out events.
- Record planned daily productivity.
- Record accumulated production at the end of the day.
- Review daily productivity results.
- View and process departmental leave requests.
- Approve or reject leave applications.
- Create and send notifications to employees in the department.

The initial system design assigns one designated Supervisor to each department. Supervisors are restricted to the records and leave requests belonging to their own departments.

### Employee

Employees use the mobile application to access their personal workforce information. They can:

- View their digital QR identification code.
- Present the QR code to a Supervisor when arriving at or leaving work.
- View their personal attendance records.
- Submit leave applications.
- Check the status of leave applications.
- Receive workplace notifications.
- View and manage their profile information.

Employees should only be able to access their own personal records and functions permitted by their assigned role.

---

## Main Features

## Attendance Management

<u>Purpose</u>

The attendance feature replaces physical attendance registers with QR-code-based attendance recording. It allows Supervisors to record employee arrival and departure times using the mobile application's scanner.

<u>How it works</u>

1. The Employee opens the Construct360 mobile application and displays their digital QR identification code.
2. The Employee presents the QR code to the Supervisor when arriving at or leaving the workplace.
3. The Supervisor opens the attendance scanning feature.
4. The Supervisor scans the Employee's QR code using the mobile device camera.
5. The backend checks the Employee's attendance state for that day.
6. The system determines whether the action should be a clock-in or clock-out.
7. The attendance information is saved in the central database and the Supervisor receives feedback.

![Employee QR identification screen](assets/employee-qr-code.png)

*Employee QR identification code.*

![Supervisor QR attendance scanning screen](assets/qr-attendance-scan.png)

*Attendance scanning through the mobile application.*

<u>Duplicate clock-in validation</u>

The backend checks whether the Employee has already clocked in for the day. If the Employee has not clocked in, the scan records a clock-in. If the Employee has already clocked in, another clock-in attempt is rejected and the Employee can only be clocked out.

This validation helps prevent duplicate clock-in records for the same employee on the same day.

<u>Attendance records</u>

Attendance records are stored centrally and include clock-in and clock-out timestamps. Employees can view their own attendance history, while Supervisors can access attendance records for employees in their assigned department.

![Employee attendance history](assets/employee-attendance-history.png)

*Employee attendance history.*

<u>Current attendance security limitation</u>

A static QR code can potentially be shared with another person. Preventing duplicate clock-ins does not, by itself, prove that the Employee is physically present at the workplace. The current system therefore relies on the Supervisor to scan each Employee's QR code and on responsible workplace procedures.

Biometric identity verification before temporarily activating a QR code is a proposed future improvement, not a feature currently claimed as implemented.

## Productivity Management

<u>Purpose</u>

The productivity feature gives Supervisors a way to compare the production planned for a working day with the actual production achieved.

The current prototype focuses on daily production recording. It does not continuously measure each employee's individual performance.

<u>How it works</u>

Productivity is recorded in two stages:

1. **Beginning of the day:** The Supervisor records the planned production target for that day.
2. **End of the day:** The Supervisor records the accumulated production achieved.

The backend compares the two values and calculates the difference between the expected and actual production.

For example:

| Measurement | Example |
|---|---:|
| Expected production | 100 units |
| Actual production | 85 units |
| Difference | -15 units |
| Target achievement | 85% |

The calculation is:

- Difference = Actual production - Expected production
- Target achievement = (Actual production / Expected production) × 100

This allows the Supervisor to see whether the daily target was achieved, exceeded or not met.

![Daily productivity recording](assets/daily-productivity.png)

*Daily productivity information.*

![Productivity records](assets/productivity-records.png)

*Productivity information displayed in the mobile application.*

<u>Current productivity limitation</u>

The current prototype does not yet account for differences in task difficulty, task complexity, individual employee output, working conditions or the time required to complete different tasks. The figures should therefore be understood as a comparison of planned and actual production, rather than a complete measure of individual employee performance.

Task-based measurements and individual targets are possible future improvements.

## Leave Management

<u>Purpose</u>

The leave management feature replaces the paper-based leave application process with a digital workflow. Employees can submit leave requests through the mobile application without having to visit reception to collect or return a physical form.

<u>How it works</u>

1. **Employee submits a request:** The Employee opens the leave management section, enters the required information and submits the application through the mobile app.
2. **Supervisor receives the request:** The request becomes available to the designated Supervisor responsible for the Employee's department.
3. **Supervisor reviews the request:** The Supervisor checks the submitted information.
4. **Supervisor makes a decision:** The Supervisor approves or rejects the request through the mobile application.
5. **System updates the status:** The backend processes the decision and updates the leave request.
6. **Employee checks the outcome:** The Employee reloads the leave request page to view the updated status.

![Employee leave requests](assets/leave-requests-overview.png)

*Leave requests displayed in the Employee mobile application.*

![Leave request status](assets/leave-request-status.png)

*Leave request status displayed to the Employee.*

![Supervisor pending leave requests](assets/pending-leave-requests.png)

*Pending leave requests available for review.*

![Supervisor leave review](assets/supervisor-leave-review.png)

*Supervisor leave request review and decision interface.*

<u>Department-based approval</u>

A leave request is routed to the designated Supervisor responsible for the Employee's department. Supervisors should not normally have access to another department's employee leave requests.

Supervisors are also employees and can apply for leave. Their requests are handled by a designated superior or authorised manager in the organisational structure.

The backend is designed to prevent conflicting decisions. If two updates were attempted for the same request, the first valid decision to commit would be saved and a later conflicting update would fail.

## Notifications and Communication

<u>Purpose</u>

The notification feature provides a central way for Supervisors to communicate workplace information to Employees. It is intended for announcements, operational updates and departmental messages.

<u>How it works</u>

- The Supervisor creates and sends a notification through the mobile application.
- The notification is directed to employees within the Supervisor's department.
- Employees receive notifications through the mobile application.
- Employees can open the notification section to view messages sent to them.

![Supervisor sending a notification](assets/supervisor-send-notification.png)

*Supervisor notification creation interface.*

![Employee notifications](assets/employee-notifications.png)

*Notifications displayed in the Employee mobile application.*

This feature helps reduce reliance on physical notices and gives Employees a convenient place to access relevant workplace information.

## Administrator Web Application

<u>Purpose</u>

The administrator web application is the administrative control centre of Construct360. It is designed exclusively for Administrators and is separate from the mobile application used by Employees and Supervisors.

<u>Main functions</u>

**Registration management**

Administrators can view incoming registration requests and approve or decline them.

**User management**

Administrators can search for registered users, view user information and manage accounts.

**Role management**

Authorised Administrators can assign roles and grant the appropriate level of access to users.

**Account blocking and unblocking**

Administrators can block accounts when access needs to be restricted and unblock accounts when access should be restored.

**Login activity**

Administrators can view available login logs to monitor account sign-in activity and investigate relevant access events. These login logs are not the same as a full audit trail of changes made to workforce records.

![Administrator login activity](assets/admin-login-activity.png)

*Administrator login activity page.*

![Administrator user management](assets/admin-user-management.png)

*Administrator user management page.*

## Registration and Access Control

<u>Purpose</u>

Registration and authentication establish user accounts and help ensure that access to Construct360 is controlled.

<u>Current registration process</u>

The current prototype includes email-domain validation. For the ROCLA implementation described in the project documentation, an email address using the approved `@rocla.com` domain passes the domain check, while personal email addresses such as Gmail or Yahoo are rejected.

Domain validation is an initial restriction. It does not independently prove that a person is an official employee. Registration requests are therefore reviewed through the Administrator web application.

<u>Approval and role assignment</u>

1. A user submits a registration request through the mobile application.
2. The backend validates the registration information, including the approved email domain.
3. The Administrator reviews the request through the web application.
4. The Administrator approves or declines the request.
5. When approving the request, the Administrator assigns the appropriate role.
6. After approval, the user can log in and access the functionality associated with their role.

<u>Role-based access control</u>

Construct360 uses role-based access control to separate the responsibilities of Employees, Supervisors and Administrators.

The backend checks a user's permissions when a restricted operation is requested. For example, an Employee attempting to access an Administrator-only operation should be denied. Access control must be enforced by the backend, not only by hiding restricted buttons in the user interface.

---

## How the System Works

The mobile application and administrator web application are separate frontends. They communicate with the same backend and central database.

### Registration flow

1. A user submits a registration request through the mobile application.
2. The backend receives and validates the request.
3. The Administrator reviews the request through the web application.
4. The Administrator approves or declines it and assigns the appropriate role.
5. The backend updates the account's access permissions.

### Attendance flow

1. The Employee presents their QR code.
2. The Supervisor scans the QR code using the mobile application.
3. The backend checks the Employee's attendance state for the day.
4. The backend validates and processes the clock-in or clock-out operation.
5. The attendance record is stored in the central database.

### Leave request flow

1. The Employee submits a leave application through the mobile application.
2. The backend routes the request to the designated departmental Supervisor.
3. The Supervisor approves or rejects the request.
4. The backend updates the leave status.
5. The Employee reloads the leave page to view the outcome.

### Overall system structure

```text
+-----------------------------+       +-----------------------------+
|   Administrator Web App     |       |     Employee Mobile App     |
|                             |       |                             |
| - Registration management   |       | - Personal attendance       |
| - User and account control  |       | - QR identification         |
| - Role management           |       | - Leave applications        |
| - Login activity logs       |       | - Notifications              |
+--------------+--------------+       +--------------+--------------+
               |                                     |
               +------------------+------------------+
                                  |
                                  v
                    +-----------------------------+
                    |        Central Backend      |
                    |                             |
                    | - Authentication            |
                    | - Role and permission checks|
                    | - Attendance validation     |
                    | - Productivity calculations |
                    | - Leave request processing  |
                    | - Business logic            |
                    +--------------+--------------+
                                   |
                                   v
                    +-----------------------------+
                    |       Central Database      |
                    |                             |
                    | - User accounts and roles   |
                    | - Attendance records        |
                    | - Productivity information  |
                    | - Leave applications         |
                    | - Notifications              |
                    | - Login activity logs       |
                    +-----------------------------+
```

---

## Security and Access Management

Construct360 separates user responsibilities and restricts access according to assigned roles.

The current prototype includes:

- Approved email-domain validation during registration.
- Administrator review of registration requests.
- Administrator-controlled role assignment.
- Backend permission checks for restricted operations.
- Department-based Supervisor access.
- Duplicate clock-in validation.
- Administrator account blocking and unblocking.
- Available login activity logs.

The project documentation also discusses additional security measures that could strengthen a future deployment. These include controlled private application distribution, HR-based employee verification, administrator approval, device management, network access control using IEEE 802.1X, device-bound client certificates (mTLS), DHCP reservations, private DNS and firewall or secure gateway restrictions.

These additional device and network controls are proposals for an enhanced security architecture. They should not be interpreted as features already implemented in the current prototype.

---

## Current Limitations and Planned Improvements

Construct360 was developed as a Minimum Viable Product (MVP). The development team prioritised essential working functionality rather than implementing every feature considered for the future.

The following table distinguishes the current prototype from proposed improvements.

| Area | Current Prototype | Proposed Future Improvement |
|---|---|---|
| Registration | Email-domain validation and registration review. | Stronger employment verification and controlled invitations. |
| User management | Administrator account and role management. | More advanced permission management. |
| Attendance | QR scanning and clock-in/clock-out validation. | Offline attendance recording and cloud synchronisation. |
| Attendance security | Duplicate clock-in prevention. | Biometric identity verification before QR activation. |
| Attendance audit | No dedicated correction history. | Full audit trail preserving previous values, new values, the person responsible, date, time and reason for changes. |
| Leave management | Mobile leave submission, approval and status checking. | More advanced approval and audit workflows. |
| Productivity | Planned versus accumulated daily production. | Task complexity and individual performance measurement. |
| Notifications | Supervisors create notifications and Employees receive them. | More advanced notification controls. |
| Login monitoring | Available login logs. | More comprehensive security monitoring. |

### Connectivity and offline attendance

The current prototype depends on an internet connection to communicate with the cloud server and record attendance. It does not yet provide a complete offline attendance solution.

A proposed improvement is to temporarily store attendance events in a local SQLite database on the Supervisor's device when there is no internet connection. Once connectivity is restored, the application could synchronise the records with the cloud database.

Each attendance event would have a unique identifier. The server could use this identifier to detect whether an event had already been processed and reject duplicate synchronisation attempts.

This offline process is a proposed improvement, not current prototype functionality.

### Attendance corrections and audit history

In the current prototype, Supervisors cannot manually edit existing attendance records in the database. The system also does not currently have a dedicated audit mechanism that records every change, who made it, when it was made and why.

A proposed attendance audit trail would preserve the original attendance value and record each subsequent correction, including:

- The previous value.
- The new value.
- The person responsible for the change.
- The date and time of the change.
- The reason for the correction.

### Productivity measurement

The current productivity feature compares planned production with accumulated production. It does not yet measure task difficulty, task complexity or individual employee output.

Future versions could introduce task-based measurements and individual targets to support more detailed and fairer productivity assessments.

### Single Sign-On

Single Sign-On (SSO) was identified during initial project planning but was excluded from the current prototype. The chosen registration workflow relies on approved email-domain validation and Administrator approval. SSO could be considered in a future version if it can be integrated without weakening those access requirements.

---

## Benefits of Construct360

Construct360 is intended to improve workforce administration in several ways.

### Reduced paperwork

Employees can complete supported workforce processes through the mobile application instead of depending on physical forms and registers.

### Improved attendance management

QR-based attendance recording gives Supervisors a digital way to record clock-in and clock-out events and allows Employees to view their personal attendance records.

### Simpler leave applications

Employees can submit leave requests remotely, and Supervisors can review and process them through the mobile application. This reduces the need to pass physical forms between employees, reception and supervisors.

### Better visibility of daily production

Supervisors can compare planned production with actual accumulated production and see whether the daily target was met.

### Improved workplace communication

Notifications provide a central way for Supervisors to share departmental announcements and operational updates with Employees.

### Controlled system access

Separate user roles and backend permission checks help ensure that users access only the functions and information relevant to their responsibilities.

### Centralised workforce information

Attendance, productivity, leave, notifications and account information are managed through a shared backend and central database rather than being treated as unrelated manual processes.

---

## Project Information

| Detail | Information |
|---|---|
| Application | Construct360 |
| Chosen client | ROCLA (Pty) Ltd |
| Development team | Constant Technology |
| Module code | XISD6329 |
| Project reference | XISD5319 |
| System type | Workforce management system |
| Main platforms | Mobile application and administrator web application |

### Development Team

- Keoagile Mafora
- Mulweli Mbedzi
- Ndivhuwo Ranwedzi
- Kopano Leshope

![Constant Technology logo](assets/constant-technology-logo.png)

### Application Profile

![Employee profile page](assets/user-profile.png)

*Profile page shared by Employee and Supervisor users.*

---

## Important Project Notes

This README describes Construct360 based on the supplied system documentation. It distinguishes between functionality included in the documented prototype and improvements proposed for future development.

The project documentation does not specify a complete implementation technology stack, deployment procedure or public installation instructions. Those details have therefore not been assumed or added here.
'''
(base/"README.md").write_text(readme, encoding="utf-8")
# zip folder for convenience including README and assets
zip_path=Path("/mnt/data/Construct360-README-GitHub-Package.zip")
with zipfile.ZipFile(zip_path,"w",zipfile.ZIP_DEFLATED) as zf:
    for f in base.rglob("*"):
        if f.is_file():
            zf.write(f, f.relative_to(base.parent))
(base/"README.md").stat().st_size, zip_path.stat().st_size
