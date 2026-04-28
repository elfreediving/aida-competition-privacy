# Privacy Policy

**AIDA Competition**

*Last updated: April 29, 2026*

---

## 1. Introduction

This Privacy Policy describes how the **AIDA Competition** mobile application ("we", "our", "the App") collects, uses, and protects information when you use our service. The App is a competition management tool designed for freediving event organizers, judges, and staff to coordinate AIDA competitions.

By using the App, you agree to the practices described in this policy.

---

## 2. Information We Collect

### 2.1 Account Information

When you create an account, we collect:

- **Email address** — used for authentication and account recovery
- **Display name** — shown to other event participants
- **Password** — stored as a secure hash via our authentication provider (Supabase Auth). We never store passwords in plain text.

### 2.2 Profile Information (Optional)

- **Profile picture** — if you choose to upload one

### 2.3 Athlete Competition Data

When events are loaded from AIDA International, the App stores:

- **Athlete name** (first and last)
- **Gender**
- **Nationality**
- **Discipline** (STA, DYN, CWT, etc.)
- **Announced Performance (AP)**
- **Personal Best (PB)**
- **Competition results** (RP, judge cards, penalty reasons)

This information is sourced from **AIDA International's public competition records** via their official API.

### 2.4 Information We Do NOT Collect

We explicitly do **not** collect or store:

- Athletes' email addresses
- Athletes' phone numbers
- Athletes' physical addresses
- Athletes' dates of birth
- Athletes' photos or face images
- Athletes' AIDA UUIDs or unique identifiers
- Location data of users
- Device identifiers for tracking
- Browsing history
- Contacts from your device

---

## 3. How We Use Information

We use the collected information to:

- Authenticate users and manage accounts
- Display competition schedules and athlete information to authorized event staff
- Submit judge results back to AIDA International (when configured by the event organizer)
- Synchronize data across devices used by event staff in real-time
- Notify users of relevant event updates within the App

We do **not** use your information for advertising, marketing, or sale to third parties.

---

## 4. Data Sharing

### 4.1 With AIDA International

When an event organizer configures AIDA integration with their API token:

- We **read** event days, start lists, and athlete information from AIDA International
- We **submit** judge results (athlete performance, cards, penalties) back to AIDA International

This sharing is essential for the App's core function and is initiated by the event organizer.

### 4.2 Within Events

Event participants (organizers, main judges, judges, staff) can see:

- Names and roles of other participants in the same event
- Athlete information for that event
- Real-time updates of judge results

Information is scoped to the event — users in one event cannot see data from another event they don't belong to.

### 4.3 Third-Party Service Providers

We use the following service providers to operate the App:

- **Supabase** ([supabase.com](https://supabase.com)) — backend authentication, database, and real-time synchronization
- **AIDA International** ([aidainternational.org](https://www.aidainternational.org)) — official source of competition data
- **Google Play Services** — app distribution and crash reporting on Android

These providers process data on our behalf and are bound by their own privacy policies.

### 4.4 Legal Requirements

We may disclose information if required by law, court order, or to protect the rights, property, or safety of users.

---

## 5. Data Retention

- **Account data** — retained while your account exists. You can request deletion at any time (see Section 8).
- **Event data** (athletes, results, logs) — automatically deleted when the event organizer deletes the event.
- **Authentication tokens** — short-lived; refreshed or expired automatically.

---

## 6. Data Security

We protect your information through:

- Encrypted connections (HTTPS) for all data transmission
- Encrypted storage at rest (handled by Supabase)
- Password hashing via industry-standard algorithms
- Role-based access control — users only see data relevant to their role and events
- Real-time access revocation when users are removed from events

While we take reasonable measures to protect your information, no system is completely secure. You are responsible for keeping your account credentials confidential.

---

## 7. Children's Privacy

The App is intended for use by adult event organizers, judges, and staff. We do not knowingly collect personal information from children under 13. AIDA International's competition records may include athletes of various ages, but no contact information for any individuals (including minors) is collected through the App.

If you believe we have collected information from a child without parental consent, please contact us so we can delete it.

---

## 8. Your Rights

You have the right to:

- **Access** the personal information we hold about you
- **Correct** inaccurate information through the App's profile settings
- **Delete** your account and associated data
- **Withdraw consent** by uninstalling the App and requesting account deletion
- **Export** your data (contact us for assistance)

To exercise these rights, contact us using the information in Section 11.

---

## 9. International Data Transfers

The App may process and store data in regions where Supabase operates (currently United States). By using the App, you consent to your data being transferred to and processed in these regions.

---

## 10. Changes to This Policy

We may update this Privacy Policy from time to time. When we make material changes, we will:

- Update the "Last updated" date at the top
- Notify users through the App if changes are significant

Continued use of the App after changes means you accept the updated policy.

---

## 11. Contact

If you have questions, concerns, or requests regarding this Privacy Policy:

**Email:** [lee33179@gmail.com]

**Developer:** [Jaehwan EL Lee]

---

## 12. Disclaimer

This App is an independent tool for managing AIDA competitions. It is not officially endorsed, affiliated with, or operated by AIDA International. AIDA International data is accessed via their public API and used in accordance with their terms.
