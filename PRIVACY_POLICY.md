# Privacy Policy

**Apnea Comp**

*Last updated: May 3, 2026*

---

## 1. Introduction

This Privacy Policy describes how the **Apnea Comp** mobile application ("we", "our", "the App") collects, uses, and protects information when you use our service. The App is a competition management tool designed for freediving event organizers, judges, and staff to coordinate AIDA-sanctioned competitions.

By using the App, you agree to the practices described in this policy.

---

## 2. Information We Collect

### 2.1 Account Information

When you create an account, we collect:

- **Email address** — used for authentication and account recovery
- **Display name** — shown to other event participants
- **Password** — stored as a secure hash via our authentication provider (Supabase Auth). We never store passwords in plain text.

### 2.2 Profile Information (Optional)

- **Profile picture** — if you choose to upload one. This image is visible to other members of any event you join, and is referenced in activity logs (see Section 2.5).

### 2.3 Athlete Competition Data

When events are loaded from AIDA International, the App stores:

- **Athlete name** (first and last)
- **Gender**
- **Nationality**
- **Discipline** (STA, DYN, CWT, etc.)
- **Announced Performance (AP)**
- **Personal Best (PB)**
- **Competition results** (RP, judge cards, penalty reasons, REMARKS)
- **Check-in signature** (digital signature drawn by the athlete on a staff device)

This information is sourced from **AIDA International's public competition records** via their official API, except for check-in signatures which are collected directly within the App.

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

### 2.5 Activity Logs

To support operational transparency during competitions, the App records significant actions taken within an event:

- **What we log** — judge result entries, schedule adjustments (OT delays), check-in operations, and member role changes
- **What each log entry contains** — the user's display name, profile picture URL (if set), the action type, the affected athlete name (if applicable), and a timestamp
- **Visibility** — log entries are visible to Organizers and Main Judges of the same event only
- **Retention** — log entries are tied to the event and are deleted when the event is deleted

Activity logs do not include any data beyond what is described above.

### 2.6 Local Device Storage (Offline Buffering)

To allow continued operation when internet connectivity is intermittent (common at pool and depth venues), the App may temporarily hold judge results in your device's memory before they reach our servers:

- **Where** — only in the App's memory while it is running. We do not write offline data to persistent device storage.
- **When** — automatically, when a judge save is attempted while the device is offline.
- **How long** — until the App synchronizes the result with our servers, which happens automatically within seconds of internet returning.
- **Visibility** — offline-buffered results are visible only on the device that created them until synchronization succeeds. Other devices in the same event do not see them.
- **Limitations** — if the App is force-closed or the device reboots before synchronization completes, offline-buffered results are lost. The App displays an "⛔ Offline" badge on affected items and warns users not to quit the App while items are pending.

This buffering does not transmit data to any third party.

---

## 3. How We Use Information

We use the collected information to:

- Authenticate users and manage accounts
- Display competition schedules and athlete information to authorized event staff
- Submit judge results back to AIDA International (when configured by the event organizer)
- Synchronize data across devices used by event staff in real-time
- Maintain activity logs for operational transparency within events
- Notify users of relevant event updates within the App

We do **not** use your information for advertising, marketing, or sale to third parties.

---

## 4. Data Sharing

### 4.1 With AIDA International

When an event organizer configures AIDA integration with their API token:

- We **read** event days, start lists, and athlete information from AIDA International
- We **submit** judge results (athlete performance, cards, penalties, remarks) back to AIDA International

This sharing is essential for the App's core function and is initiated by the event organizer.

### 4.2 Within Events

Event participants (organizers, main judges, judges, staff) can see:

- Names, profile pictures, and roles of other participants in the same event
- Athlete information for that event
- Real-time updates of judge results
- Activity logs (Organizers and Main Judges only)

Information is scoped to the event — users in one event cannot see data from another event they don't belong to.

### 4.3 Third-Party Service Providers

We use the following service providers to operate the App:

- **Supabase** ([supabase.com](https://supabase.com)) — backend authentication, database, real-time synchronization, and storage of profile pictures
- **AIDA International** ([aidainternational.org](https://www.aidainternational.org)) — official source of competition data
- **Apple App Store** and **Google Play Services** — app distribution and crash reporting

These providers process data on our behalf and are bound by their own privacy policies.

### 4.4 Legal Requirements

We may disclose information if required by law, court order, or to protect the rights, property, or safety of users.

---

## 5. Data Retention

- **Account data** — retained while your account exists. You can request deletion at any time (see Section 8).
- **Event data** (athletes, results, logs, signatures) — automatically deleted when the event organizer deletes the event.
- **Offline-buffered results** — held in device memory only; either synchronized to our servers within seconds of internet returning, or lost if the App is closed before sync.
- **Authentication tokens** — short-lived; refreshed or expired automatically.

---

## 6. Data Security

We protect your information through multiple layers of security:

### Transport & Storage
- All data is transmitted over encrypted HTTPS connections
- Data is encrypted at rest by our infrastructure provider (Supabase)
- Passwords are hashed using industry-standard algorithms; we never store plain-text passwords

### Database-Level Access Control
- **Row-Level Security (RLS)** is enforced at the database level on all tables containing user or event data
- Users can only access data for events they belong to
- Pending or unapproved members cannot access event data
- Permissions are checked on every query, not just at login

### Role-Based Permissions
- **Main Judge / Organizer** — can manage events, members, and competition data; view activity logs
- **Judge** — can view and submit competition results
- **Staff** — can view event data
- Permissions are scoped per-event; a judge in one event has no access to another

### AIDA API Token Protection
- AIDA API tokens (used to sync with AIDA International) are stored encrypted in the database
- Only main_judge and organizer roles can retrieve tokens, enforced through restricted database functions
- Other roles (judge, staff) cannot access tokens, even if they have access to other event data
- Tokens are masked in the user interface; users must explicitly choose to reveal them

### Session & Access
- Authentication tokens are short-lived and refreshed automatically
- Access is revoked in real-time when users are removed from events
- Account credentials are your responsibility; never share them

While we take reasonable measures to protect your information, no system is completely secure. You are responsible for keeping your account credentials confidential and reporting any suspicious activity.

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

**Email:** lee33179@gmail.com

**Developer:** Apnea Comp

---

## 12. Disclaimer

This App is an independent tool for managing AIDA competitions. It is not officially endorsed, affiliated with, or operated by AIDA International. AIDA International data is accessed via their public API and used in accordance with their terms.
