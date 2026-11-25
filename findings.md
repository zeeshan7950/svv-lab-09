# MediTrack SRS — Consolidated Findings

## Review summary

The checklist identifies major clarity, consistency, testability and completeness problems. The most serious concerns are the contradictory appointment-duration requirements, insufficient double-booking controls, weak privacy requirements and missing support for emergency walk-ins and elderly patients.

**Note:** The two run files above are worked examples. In the actual paired exercise, both students must complete their own runs separately, record real start/end times, and then agree on this findings list.

## Agreed findings

| Finding ID | Related requirement(s) | Problem | Why it matters | Recommended improvement |
|---|---|---|---|---|
| F-01 | R-04, R-05 | Appointment duration is contradictory: fixed at 15 minutes versus configurable from 10 to 30 minutes. | Developers and testers cannot know which rule to implement. | Clinic must decide whether duration is fixed or configurable; rewrite both requirements consistently. |
| F-02 | R-03 | “Prevent double bookings” is too general and does not describe simultaneous booking behaviour. | Two users may attempt to reserve the same slot at the same time. | Specify that a doctor/time slot can be confirmed for only one appointment, including concurrent requests; define the expected system response to the losing request. |
| F-03 | R-02, R-12 | “Quickly” and “normal working hours” are not measurable or defined. | Performance and availability cannot be objectively tested. | State response-time targets, expected operating days/hours and availability target. |
| F-04 | R-06 | Reminder timing and delivery channel are missing. | Patients may still forget appointments. | Specify reminder channel(s), timing and what happens if delivery fails. |
| F-05 | R-07 | Requirement combines multiple actions and permits cancellation at any time without defining late-cancellation handling. | Schedule changes may be unclear and reception staff may not know how to handle last-minute cancellations. | Split into separate requirements for cancellation, schedule update and receptionist notification; define cancellation rules. |
| F-06 | R-08 | “User-friendly for all age groups” is subjective and has no accessibility criteria. | Elderly patients may be unable to use online booking. | Define testable accessibility and usability requirements, including readable text, clear navigation and support for users who need assistance. |
| F-07 | R-09 | “Stored securely” does not define access control, protection or record retention. | Medical information may be exposed or retained improperly. | Define role-based access, audit logging, protection of data and retention/deletion rules in line with clinic policy and applicable law. |
| F-08 | R-10 | Walk-in booking is mentioned, but emergency walk-ins and priority handling are not. | Emergency patients may be treated like routine bookings or overlooked. | Define how receptionists register emergency walk-ins and how urgent cases are escalated/priority-handled by clinic staff. |
| F-09 | R-11 | “Active appointment” is undefined. | The three-appointment limit may be applied inconsistently. | Define which statuses count as active and what happens when a patient reaches the limit. |
| F-10 | R-13 | “As per clinic policy” refers to a policy that is not identified or included. | Payment handling may be inconsistent. | Attach or reference the approved policy and state the system actions required for overdue payments. |
| F-11 | R-14 | Doctor schedule view is underspecified. | Doctors may not see the information needed to manage their day. | Specify the schedule fields and permitted actions, while protecting patient information. |
| F-12 | No requirement | Clinic administrator is a named user but has no defined system responsibilities. | An important stakeholder’s needs are omitted. | Add administrator requirements for relevant configuration, user management and reporting, with appropriate permissions. |
| F-13 | R-02 / missing requirement | No explicit peak-load requirement for busy Monday mornings. | The system may become slow or unavailable when demand is highest. | Define expected concurrent users/booking volume and measurable performance under peak load. |

## Risks covered

1. Double booking or concurrent booking conflict.
2. Patients forgetting appointments because reminders are unclear.
3. Exposure or improper retention of private medical information.
4. Elderly patients being unable to use the booking system.
5. Emergency walk-in patients not receiving appropriate attention.
6. Monday-morning overload and slow response.
7. Confusion caused by conflicting appointment-duration rules.
8. Inconsistent cancellation and overdue-payment handling.

## Stakeholder coverage

- **Patient:** online booking, reminders, cancellation, appointment limit and accessibility.
- **Doctor:** appointment duration, availability checks and daily schedule.
- **Receptionist:** walk-in/emergency handling, cancellation notifications and payment handling.
- **Clinic administrator:** missing administrator functions and permissions.
- **Data protection officer:** access control, privacy, audit and retention requirements.

## Overall conclusion

The SRS is **not ready for contract approval in its current form**. The clinic should resolve the appointment-duration conflict and clarify double-booking prevention, privacy/access control, reminders, accessibility, emergency walk-ins and measurable performance before signing. The revised SRS should then be reviewed again using an updated checklist.
