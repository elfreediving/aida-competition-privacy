---
title: Privacy Policy
---

# Privacy Policy

**Apnea Comp**

*Last updated: August 22, 2026*

---


## 1. Introduction

This Privacy Policy describes how the **Apnea Comp** mobile application (“we”, “our”, “the App”) collects, uses, and protects information when you use our service. The App is a competition management tool designed for freediving event organizers, judges, staff, and athletes participating in AIDA-sanctioned competitions.

By using the App, you agree to the practices described in this policy.

---


## 2. Information We Collect

### 2.1 Account Information

When you create an account, we collect:

- **Email address** — used for authentication and account recovery
- **Display name** — shown to other event participants
- **Password** — stored as a secure hash via our authentication provider (Supabase Auth). We never store passwords in plain text.


**Signing in with Apple or Google.** You may sign in using your Apple or Google account instead of an email-and-password login. When you do, we receive your **name** and **email address** from Apple or Google to create or identify your account. If you use **Sign in with Apple** and choose to hide your email, Apple gives us a private relay email address instead of your real one, which we use the same way as any other email. We never receive your Apple or Google password — sign-in is handled by the provider together with our authentication provider (Supabase Auth).


### 2.2 Profile Information (Optional)

- **Profile picture** — if you choose to upload one. This image is visible to other members of any event you join, and is referenced in activity logs (see Section 2.6).


### 2.3 Athlete Account Linking (For Athletes)

If you sign up as an athlete to view start lists and your own results, the App stores:

- **AIDA athlete UUID** — the permanent identifier from AIDA International used to match your account to your appearances in event start lists. This UUID is associated with you only after the event organizer’s invite code is verified or your name is matched against an event start list and approved.
- **Synced display name** — your first and last name as published in AIDA’s start list, copied to your profile during the linking step
- **AIDA search queries** — when you use the “Find me on AIDA” feature to locate your athlete profile, the name you type is sent to AIDA International’s public athlete-search service to retrieve matching profiles. Only the text you type is transmitted; no account credentials are included (see Section 4.1).


This data is held only on your own profile to enable read-only access to events you participate in.

### 2.4 Athlete Competition Data (Loaded From AIDA)

When events are loaded from AIDA International by an event organizer, the App stores:

- **Athlete name** (first and last)
- **Gender**
- **Nationality**
- **Discipline** (STA, DYN, CWT, etc.)
- **Announced Performance (AP)**
- **Personal Best (PB)**
- **Competition results** (RP, judge cards, penalty reasons, REMARKS)
- **Points** — competition points calculated from the result
- **Entry type** — whether an entry is a regular start, an *opener* (a warm-up entry excluded from rankings and not sent to AIDA), or a *re-swim* (a re-performance approved through a protest)
- **Validity flag** — when an athlete re-swims, the original entry is marked *invalidated* so it is excluded from rankings; it still appears in Results
- **Check-in status** — a boolean flag indicating whether the athlete signed in at the event. The App displays a signature pad during check-in so the athlete can confirm presence, but **the signature image itself is never stored** — only the fact that a signature occurred.


This information is sourced from **AIDA International’s public competition records** via their official API, except for check-in status which is recorded directly within the App.

### 2.5 Information We Do NOT Collect

We explicitly do **not** collect or store:

- Athletes’ email addresses (other than the athlete’s own email if they have an account)
- Athletes’ phone numbers
- Athletes’ physical addresses
- Athletes’ photos or face images
- Check-in signature images (only a boolean flag is stored)
- Location data of users
- Device identifiers for tracking
- Browsing history
- Contacts from your device


### 2.6 Activity Logs

To support operational transparency during competitions, the App records significant actions taken within an event:

- **What we log** — judge result entries, schedule adjustments (OT delays), check-in operations, and member role changes
- **What each log entry contains** — the user’s display name, profile picture URL (if set), the action type, the affected athlete name (if applicable), and a timestamp
- **Visibility** — log entries are visible to Organizers and Main Judges of the same event only
- **Retention** — log entries are tied to the event and are deleted when the event is deleted


Activity logs do not include any data beyond what is described above.

### 2.7 Push Notification Data

To deliver event-related notifications to your device, the App stores:

- **OneSignal Subscription ID** — a device-specific identifier issued by our push notification provider (OneSignal). Used solely as the destination address for notifications.
- **OneSignal external user ID** — your account ID, linked to the Subscription ID so notifications can be addressed to your account regardless of device.
- **Subscription timestamp** — last update time, used to detect stale subscriptions


These values are stored in your account profile. The Subscription ID is automatically cleared when notifications are disabled, the App is uninstalled, or the device’s notification permission is revoked.

**Note:** Apnea Comp previously used Firebase Cloud Messaging (FCM) for push delivery. As of May 2026, push notification infrastructure has been migrated to OneSignal. See Section 4.3 for details on the third-party providers involved.

### 2.8 Local Device Storage

The App stores limited data locally on your device for two purposes:

**Offline Buffering (Judge Results)**

To allow continued operation when internet connectivity is intermittent (common at pool and depth venues), the App may temporarily hold judge results in your device’s memory before they reach our servers:

- **Where** — only in the App’s memory while it is running. Offline-buffered judge results are not written to persistent device storage.
- **When** — automatically, when a judge save is attempted while the device is offline.
- **How long** — until the App synchronizes the result with our servers, which happens automatically within seconds of internet returning.
- **Visibility** — offline-buffered results are visible only on the device that created them until synchronization succeeds. Other devices in the same event do not see them.
- **Limitations** — if the App is force-closed or the device reboots before synchronization completes, offline-buffered results are lost. The App displays an “⛔ Offline” badge on affected items and warns users not to quit the App while items are pending.

**Login Convenience (Remember Email / Password)**

The login screen offers two optional toggles that store credentials locally so they appear pre-filled on subsequent logins:

- **Remember email** — if enabled, your email address is saved to your device’s standard local storage (SharedPreferences on Android, NSUserDefaults on iOS).
- **Remember password** — if enabled, your password is saved to your device’s **secure keystore** (iOS Keychain / Android EncryptedSharedPreferences, AES-256, encrypted by the operating system). It is never stored in plain text and never transmitted to our servers or any third party. It is used only to pre-fill the login form and restore your session on the same device.
- **Where** — only on your device. This information is not transmitted to our servers or any third party.
- **How to remove** — uncheck the option on the next login, sign out of the App (which clears the stored credentials), or uninstall the App.

**Display Preferences**

Your theme choice (light / dark / system) and app language are saved locally (SharedPreferences) so the App remembers them between launches. These are preference settings only and contain no personal information.

Neither offline buffering, login convenience, nor display-preference storage transmits data to any third party.

### 2.9 Protest Data

When a protest is filed under AIDA competition rules (Rulebook 17.7), the App stores a protest record containing:

- **Protest reason** — free text entered by the person who files the protest
- **Athlete signature** and, where applicable, **Jury signature** — captured as a hand-drawn image and stored (base64-encoded) inside the protest record. Unlike the check-in signature pad, **protest signatures are retained**, because a signed protest is part of the official competition record.
- **Generated protest form** — a PDF that embeds the reason and signatures, stored in our backend file storage (Supabase Storage)
- **Decision and amendments** — the jury’s decision (accepted / rejected / withdrawn) and, if accepted, the amended result (card, RP, remarks)

**Visibility** — protest records are visible to the event’s staff (Organizer, Main Judge, Judge) and to the athlete the protest concerns. Protest activity triggers push notifications (see Section 3).

### 2.10 Document Submissions (Consent Forms & Medical Statement)

When an athlete joins an event, the App may collect and store consent and eligibility documents required by the organizer:

- **Competition Entry Form** — gender, date of birth, country of birth, citizenship, personal-best performances per discipline, and **health-related history you choose to declare** (last pressure injury / barotrauma date, last black-out date, last medical examination date).
- **Image Rights Consent** and **Liability Waiver** — your name, the event name and place, the date of signing, and your hand-drawn signature.
- **Medical Statement (optional)** — a doctor's fitness declaration containing the examination/issue date and the physician's name, phone number, and hand-drawn signature. Because it certifies your health, this is **sensitive health information**. A medical statement is valid for one year and, at your choice, is stored on your own profile so it can be reused for future events.
- **Signatures** — athlete, witness, and physician signatures are captured as hand-drawn images and embedded into the generated forms. Unlike the check-in signature, these are **retained** as part of the consent record.
- **Uploaded files** — if you submit a document as a photo or scan instead of filling it in the App, the image file is stored.
- **Generated PDFs** — forms you complete in the App are rendered to PDF and stored in our backend file storage (Supabase Storage).

**Visibility** — submitted event documents are visible to the event's Organizer and Main Judge for verification, who may also download them in bulk as a ZIP archive. If you declare an injury or black-out date, staff are prompted to manually verify your medical statement.

**Reminders** — if mandatory documents are not submitted by the day before the event, you may receive a push notification listing the missing documents.

---


## 3. How We Use Information

We use the collected information to:

- Authenticate users and manage accounts
- Display competition schedules and athlete information to authorized event staff
- Display start lists and personal results to athletes who have linked their accounts
- Submit judge results back to AIDA International (when configured by the event organizer)
- Synchronize data across devices used by event staff in real-time
- Maintain activity logs for operational transparency within events
- Manage protests filed under AIDA competition rules, including capturing signatures and recording the jury’s decision and any amended result
- Check a server-side minimum supported app version (a public configuration value) to prompt users to update; this check transmits no personal data
- Send push notifications via OneSignal, including:
  * **Manual notifications** triggered by event organizers (start list publication, unofficial results, official results)
  * **Automatic notifications** triggered by event state (schedule changes / OT delays affecting specific athletes; check-in deadline reminders sent to athletes who have not yet checked in; protest activity — filed, awaiting athlete signature, decided)
  * Notification text is localized to the recipient’s app language


We do **not** use your information for advertising, marketing, or sale to third parties.

---


## 4. Data Sharing

### 4.1 With AIDA International

When an event organizer configures AIDA integration with their API token:

- We **read** event days, start lists, and athlete information from AIDA International
- We **submit** judge results (athlete performance, cards, penalties, remarks) back to AIDA International


This sharing is essential for the App’s core function and is initiated by the event organizer.

Separately, when an athlete uses the **“Find me on AIDA”** feature, the App sends the name text you type to AIDA International’s public athlete-search service in order to retrieve matching athlete profiles. Only the search text is sent; no account credentials or other personal data are included.

### 4.2 Within Events

Event participants (organizers, main judges, judges, staff) can see:

- Names, profile pictures, and roles of other participants in the same event
- Athlete information for that event
- Real-time updates of judge results
- Activity logs (Organizers and Main Judges only)


Athletes who have linked their account can see:

- Start lists for events they appear in
- Their own competition results


Information is scoped to the event — users in one event cannot see data from another event they don’t belong to. Athletes do not see other athletes’ personal account information.

### 4.3 Third-Party Service Providers

We use the following service providers to operate the App:

- **Supabase** ([supabase.com](https://supabase.com)) — backend authentication, database, real-time synchronization, and file storage (profile pictures and generated protest form PDFs)
- **Apple — Sign in with Apple** — if you choose to sign in with Apple, Apple authenticates you and shares your name and email (or a private relay email) with us. See Apple's privacy policy at [apple.com/legal/privacy](https://www.apple.com/legal/privacy/).
- **Google — Google Sign-In** — if you choose to sign in with Google, Google authenticates you and shares your name and email with us. See Google's privacy policy at [policies.google.com/privacy](https://policies.google.com/privacy)
- **OneSignal** ([onesignal.com](https://onesignal.com)) — delivery of push notifications to mobile devices. When a notification is sent, the destination Subscription ID, the notification title, and the notification body pass through OneSignal’s infrastructure. OneSignal may also collect device-level metadata (device model, OS version, language, timezone, country, IP address) for delivery optimization. See OneSignal’s privacy policy at [onesignal.com/privacy](https://onesignal.com/privacy_policy). OneSignal in turn forwards the notification payload to platform-level push services — Apple Push Notification service (APNs) for iOS and Firebase Cloud Messaging (FCM) for Android — for final delivery to the device.
- **AIDA International** ([aidainternational.org](https://www.aidainternational.org)) — official source of competition data
- **Apple App Store** and **Google Play Services** — app distribution and crash reporting
- **Sentry** ([sentry.io](https://sentry.io)) — automated error and crash diagnostics. When the App encounters a crash or an unexpected error, a diagnostic report is sent containing the type of error, the code location where it occurred, the app version and build number, the device model, and the operating system version. This reporting is deliberately configured for **data minimisation**: it does **not** send your IP address or device identifiers, does **not** capture screenshots or screen contents, does **not** include request bodies, authentication tokens, or your account information, and does **not** track usage or behaviour. Text contained in error messages is scrubbed before transmission — email addresses are masked and long encoded values (such as captured signature images) are redacted — and if that scrubbing cannot be completed the report is discarded rather than sent. Reports are used solely to find and fix defects, and are especially important for the safety-related features of the App. Sentry processes this data in the United States; see Sentry's privacy policy at [sentry.io/privacy](https://sentry.io/privacy/).


These providers process data on our behalf and are bound by their own privacy policies.

### 4.4 Legal Requirements

We may disclose information if required by law, court order, or to protect the rights, property, or safety of users.

### 4.5 Shared Sign-In Across ELfreediving Apps

Apnea Comp uses a shared sign-in system operated by ELfreediving. A single account — whether created with email/password or through Apple or Google sign-in — can be used to sign in to other ELfreediving apps. For sign-in purposes, your **account credentials and basic profile** (email, display name, and profile picture) are shared across these apps. Your **Apnea Comp competition data** (events, start lists, results, documents, and protests) is scoped to Apnea Comp and is **not** shared with other apps.

---


## 5. Data Retention

- **Account data** — retained while your account exists. You can request deletion at any time (see Section 8).
- **Event data** (athletes, results, logs, check-in status, protests) — automatically deleted when the event organizer deletes the event.
- **Protest data** (reason, signatures, decisions) — held as part of the event and deleted together with the event when the organizer deletes it. The generated protest PDF stored in our file storage is removed when an individual protest is deleted, and in all cases is **automatically deleted 30 days after it is generated**.
- **Document submissions** (competition entry, image rights, liability, and event-submitted medical) — kept as part of the event and **automatically deleted 15 days after the event ends**. A medical statement you save to your own profile is retained for its one-year validity and can be withdrawn at any time.
- **OneSignal Subscription ID** — cleared automatically when you disable notifications, uninstall the App, or revoke notification permissions on your device. Subscriptions that fail repeatedly (e.g., the device is no longer reachable) are also cleared automatically by OneSignal.
- **Locally stored credentials** (Remember email / Remember password) — kept on your device until you disable the option, sign out, or uninstall the App.
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

- **Main Judge / Organizer** — can manage events, members, and competition data; view activity logs; send manual push notifications
- **Judge** — can view and submit competition results
- **Staff** — can view event data
- **Athlete** — read-only access to start lists and personal competition results
- Permissions are scoped per-event; a judge in one event has no access to another


### AIDA API Token Protection

- AIDA API tokens (used to sync with AIDA International) are stored encrypted in the database
- Only main_judge and organizer roles can retrieve tokens, enforced through restricted database functions
- Other roles (judge, staff, athlete) cannot access tokens, even if they have access to other event data
- Tokens are masked in the user interface; users must explicitly choose to reveal them


### Session & Access

- Authentication tokens are short-lived and refreshed automatically
- Access is revoked in real-time when users are removed from events
- Account credentials are your responsibility; never share them


While we take reasonable measures to protect your information, no system is completely secure. You are responsible for keeping your account credentials confidential and reporting any suspicious activity.

---


## 7. Children’s Privacy

The App is intended for use by adult event organizers, judges, staff, and athletes (typically 18 and older). We do not knowingly collect personal information from children under 13. AIDA International’s competition records may include athletes of various ages, but no contact information for any individuals (including minors) is collected through the App.

If you believe we have collected information from a child without parental consent, please contact us so we can delete it.

---


## 8. Your Rights

You have the right to:

- **Access** the personal information we hold about you
- **Correct** inaccurate information through the App’s profile settings
- **Delete** your account and associated data
- **Withdraw consent** by uninstalling the App and requesting account deletion
- **Disable notifications** through your device’s system settings or the App’s notification preferences. Disabling notifications immediately stops your push subscription from being used and clears it from our servers and from OneSignal.
- **Export** your data (contact us for assistance)


To exercise these rights, contact us using the information in Section 11.

---


## 9. International Data Transfers

The App may process and store data in regions where our service providers operate. Supabase data is stored in South Korea (Seoul region) and Japan (Tokyo region). Push notifications are routed through OneSignal, which operates globally and may process notification metadata in the United States and other regions where their infrastructure is located. OneSignal in turn forwards notifications through Apple Push Notification service (APNs) and Firebase Cloud Messaging (FCM), which also operate globally. Error and crash diagnostics are processed by Sentry in the United States; these reports contain no personal information (see Section 4.3). By using the App, you consent to your data being transferred to and processed in these regions.

---


## 10. Changes to This Policy

We may update this Privacy Policy from time to time. When we make material changes, we will:

- Update the “Last updated” date at the top
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
