# Workforce, Attendance & Payroll ERP

A multi-tenant business application connecting employee records, biometric attendance, shift policies, payroll, and employee self-service across Web, Android, and Windows clients.

**Company:** Drunall Technologies  
**Project type:** Workforce Management & Payroll ERP  
**Repository type:** Public product case study  
**Source code:** Private  

[Visit the Web Portal](https://erp.jdpatidar.com/login)

> This repository contains product documentation only. The live portal requires authorized access and is not an unrestricted public demo.

## Overview

The platform brings workforce administration into a shared system for company administrators, employees, and platform operators.

Attendance records can originate from compatible biometric terminals or mobile punches. Configured shift and payroll rules connect these records with working hours, overtime, deductions, and salary processing.

A shared React frontend supports the browser experience and is packaged for Android using Capacitor and Windows using Electron.

## Business Challenge

Workforce administration requires several connected activities:

- Maintaining employee records for different companies.
- Collecting attendance from hardware and mobile devices.
- Interpreting multiple punches, breaks, and split shifts.
- Applying grace periods, overtime, and deduction rules.
- Processing salary advances and monthly payroll.
- Giving employees access to attendance, leave, and payslips.
- Maintaining consistent application releases across platforms.

The platform connects these activities through a common backend and company-specific workflows.

## Solution

The implementation combines:

- A multi-tenant backend for company-specific records.
- An administration portal for workforce operations.
- Employee self-service interfaces.
- ADMS/iClock biometric device integration.
- Attendance processing and configurable payroll rules.
- Android and Windows clients.
- Notifications, document generation, and release tooling.

## Main Capabilities

### 1. Multi-Tenant Company Management

The platform supports multiple organizations with company-specific employee, attendance, shift, and payroll records.

Platform administration includes:

- Company onboarding.
- Subscription and plan-limit management.
- License extensions.
- Platform-level activity summaries.
- Biometric communication monitoring.

### 2. Employee Management

Company administrators can maintain an employee directory and manage records used by attendance, payroll, and self-service workflows.

The employee record connects workforce administration with monthly attendance and salary information.

### 3. Biometric Attendance Integration

The backend integrates with compatible devices using the ADMS/iClock push protocol.

The integration handles:

- Device registration and company mapping.
- Incoming attendance punch logs.
- Device requests for pending commands.
- Command execution responses.
- Device communication monitoring.

Compatibility depends on the device model, firmware, and supported protocol configuration.

### 4. Attendance & Shift Processing

Attendance processing supports:

- Multiple punches per day.
- Split shifts.
- Break tracking.
- Shift-based working hours.
- Grace-period policies.
- Late arrival and early departure rules.
- Manual attendance adjustments.
- Monthly summaries and color-coded Excel exports.

### 5. Payroll & Payslips

Payroll processing connects configured salary rules with attendance records.

Supported components include:

- Gross-to-net salary calculations.
- Overtime.
- Allowances.
- Penalty deductions.
- Salary advances.
- PDF payslip generation.
- Payslip sharing through the configured WhatsApp integration.

### 6. Employee Self-Service

Employees can access a mobile-oriented interface for daily workforce tasks.

Features include:

- Punch-in and punch-out.
- GPS location capture for mobile punches.
- Break start and end actions.
- Daily punch status and working hours.
- Monthly attendance calendar.
- Leave requests and balances.
- Salary advance requests and history.
- Payroll history and payslip downloads.
- Access PIN changes.

### 7. Dashboards & Reports

Company dashboards provide attendance summaries, including present, absent, late, and on-leave counts.

Reporting supports reviewing daily records, monthly attendance, and payroll information.

### 8. Notifications & Communication

Firebase Cloud Messaging supports notifications for events such as attendance activity, leave approvals, and announcements.

The platform also includes SMTP email delivery and WhatsApp integration for supported communication workflows.

### 9. Cross-Platform Applications

| Client | Implementation |
| --- | --- |
| Web | React application built with Vite |
| Android | Capacitor application shell |
| Windows | Electron desktop application |

The clients communicate with a shared REST API.

### 10. Release & Update Management

Release tooling coordinates Android and Windows application versions.

The documented workflow includes:

- Shared version updates across application configuration.
- Android release packaging.
- Windows installer packaging.
- Mobile version checks and update prompts.

## Technology Stack

The following stack is documented for this project.

| Layer | Technologies |
| --- | --- |
| Frontend | React 18, Vite 5 |
| UI | Tailwind CSS, Radix UI, Lucide Icons |
| Tables | TanStack Table |
| Forms | React Hook Form, Zod |
| Backend | PHP, Laravel Lumen 10 |
| Database | MySQL |
| Authentication | JWT |
| PDF Generation | DomPDF |
| Push Notifications | Firebase Cloud Messaging |
| Mobile | Capacitor |
| Desktop | Electron, electron-builder |
| Device Integration | ADMS/iClock |
| Messaging | OpenWA integration, SMTP email |

## Architecture Overview

The application uses a shared backend serving three client environments.

- **Client layer:** Web, Android, and Windows interfaces.
- **API layer:** Authentication, tenant context, workforce workflows, and payroll processing.
- **Integration layer:** Biometric device communication, push notifications, and messaging.
- **Data layer:** Company-specific operational records in MySQL.

Company administrators, employees, and platform administrators use separate interfaces and access contexts.

## Example Workflows

### Biometric Attendance

1. Register a compatible attendance device.
2. Associate it with the relevant company.
3. Receive employee punch events.
4. Process punches against configured attendance and shift rules.
5. Review records and monthly summaries.

### Mobile Attendance

1. The employee signs in.
2. The employee records a punch with location information.
3. The platform updates daily attendance status.
4. The employee reviews punches and working hours.
5. Administrators review the attendance record.

### Monthly Payroll

1. Review attendance records and applicable adjustments.
2. Apply configured salary and attendance policies.
3. Calculate overtime, allowances, deductions, and advances.
4. Generate payroll records and PDF payslips.
5. Make payslips available through supported employee workflows.

### Leave Requests

1. An employee submits a leave request.
2. The request enters the administrative review workflow.
3. The decision updates the employee's leave information.
4. Notifications communicate relevant status changes.

## Engineering Considerations

### Company Context Across Modules

Employee, attendance, shift, and payroll operations must consistently use the correct company context.

### Hardware Data Interpretation

Device communication requires translating protocol-specific events into records that the attendance system can process.

### Attendance-to-Payroll Consistency

Multiple punches, breaks, shift boundaries, grace periods, and manual adjustments affect salary calculations and require consistent handling.

### Shared Application Behavior

Web, Android, and Windows clients share application functionality while handling platform-specific capabilities such as geolocation, notifications, and packaging.

### Coordinated Releases

Version coordination helps keep application update metadata aligned with the packaged releases.

## Functional Outcomes

The platform provides:

- Centralized workforce administration.
- Connected biometric and mobile attendance workflows.
- Configurable attendance and payroll processing.
- Employee access to attendance, leave, advances, and payslips.
- Web, Android, and Windows access through a shared backend.
- Reporting and communication tools for daily operations.

No quantified productivity, accuracy, or performance improvement claims are presented in this case study.

## Live Portal

[Open the ERP Login Page](https://erp.jdpatidar.com/login)

Access requires an authorized account. Contact us to discuss a guided product walkthrough.

## Repository Scope

This is a documentation-only portfolio repository.

It does not include:

- Application source code.
- Employee or company data.
- Database exports.
- Credentials or environment configuration.
- Internal deployment instructions.

The application source code remains private.

## Credits & Contact

**Company:** Drunall Technologies  
**Portfolio contact:** Jagdish Patidar — Founder & CEO

- [Drunall Technologies](https://www.drunall.com)
- [Jagdish Patidar — Portfolio](https://jdpatidar.com)
- [LinkedIn](https://www.linkedin.com/in/jdpatidar/)

For workforce management, attendance integration, payroll, or custom business software requirements, connect through the links above.
