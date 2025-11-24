# Technical Constraints

## Core Platform
*   **Single Codeline**: All customers run on the same version. No custom code branches allowed.
*   **Configurability**: All logic must be definable via "Calculated Fields" or configuration, not hard-coded.
*   **Object Model**: Must adhere to the strict Student Object Model (Student, Course, Course Section, Program of Study).

## Security & Compliance
*   **RBAC**: Strict Role-Based Access Control. Advisors cannot see financial aid data unless explicitly granted.
*   **FERPA**: All student data views must be FERPA compliant (audit logs for every view).
*   **WCAG 2.1 AA**: All UI components must meet accessibility standards.

## Performance
*   **Registration Peak Load**: System must handle 50k concurrent registrations (the "9:00 AM rush").
*   **Latency**: Page loads must be under 200ms for core workflows.
