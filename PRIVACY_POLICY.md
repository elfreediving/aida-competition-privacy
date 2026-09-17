---
title: Privacy Policy
---

# Privacy Policy

**Apnea Comp**

*Last updated: September 18, 2026*

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
- **AIDA public profile lookups** — when anyone opens an athlete profile in the App, the App requests that athlete’s public profile page and public results page from AIDA International’s website using the athlete’s AIDA UUID, and displays the career records, national / continental / world rankings, competition history and profile photograph that AIDA publishes there. No account credentials are sent, and we do not store a copy: the result is held in the App’s memory for the current session only and is discarded when the App restarts.


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
- **Check-in status** — whether the athlete is pending, checked in, checked in late, or a no-show (DNS), together with the check-in time. A late check-in or DNS carries a competition penalty under AIDA rules, and the App may mark an athlete late automatically once the check-in deadline has passed. The App displays a signature pad during check-in so the athlete can confirm presence, but **the signature image itself is never stored** — only the fact that a signature occurred.
- **Risk marking** — a safety flag that event staff may set on an athlete (see Section 2.11)


This information is sourced from **AIDA International’s public competition records** via their official API, except for check-in status and risk marking, which are recorded directly within the App.

### 2.5 Information We Do NOT Collect

We explicitly do **not** collect or store:

- Athletes’ email addresses, other than the email address of an athlete who has their own account, and the addresses of event members shown to organizers
- Athletes’ phone numbers, other than the physician’s contact number that appears on a medical statement you choose to submit
- Athletes’ physical addresses
- Check-in signature images (only a boolean flag is stored)
- Location data of users
- Advertising or cross-app tracking identifiers, and any use of your data for advertising
- Browsing history
- Contacts from your device


We do store a randomly generated identifier for the device you sign in on. It is created by the App, is not derived from any hardware identifier, and is used only to enforce that one account is signed in on one device at a time and to keep a Speaker Mode device signed in during an event.

We do not store athletes’ face photographs. A profile picture you upload yourself is stored (Section 2.2), and athlete profile photographs published by AIDA International are displayed in the App by loading them from AIDA’s public website when a profile is opened (Section 2.3).


### 2.6 Activity Logs

To support operational transparency during competitions, the App records significant actions taken within an event:

- **What we log** — judge result entries and corrections, schedule adjustments (OT delays), check-in operations (including automatic late marking by the system), setup and start-list changes, notification sends and cancellations, member role changes, and actions taken on an athlete’s medical statement (revocation, restoration, and confirmation of a prior black-out at check-in).
- **What each log entry contains** — the user’s display name, profile picture URL (if set), the action type, the affected athlete name (if applicable), a timestamp, and a structured detail record describing what changed (for example the previous and new result values).
- **Separate judging audit** — every change to a saved judge result, including attempts that the server blocked, is additionally recorded in an audit table holding the acting user’s email address and the values before and after the change. This exists so that a disputed result can be reconstructed. It is readable only by the event’s Organizer and Main Judge and has no screen in the App.
- **Visibility** — the activity log screen is available to Organizers and Main Judges. Log entries are stored inside the event and are technically readable by approved members of the same event through our API.
- **Retention** — log entries and the judging audit are kept for as long as the event record exists. They are not linked to the event by a database constraint, so deleting an event does not automatically remove them; see Section 5.


### 2.7 Push Notification Data

To deliver event-related notifications to your device, the App stores:

- **OneSignal Subscription ID** — a device-specific identifier issued by our push notification provider (OneSignal). Used solely as the destination address for notifications.
- **OneSignal external user ID** — your account ID, linked to the Subscription ID so notifications can be addressed to your account regardless of device.
- **Subscription timestamp** — last update time, used to detect stale subscriptions


These values are stored in your account profile. The Subscription ID is cleared when you sign out of the App, when a different account signs in on the same device, and automatically when OneSignal reports that the subscription is no longer valid (for example after the App is uninstalled or notification permission is withdrawn).

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

**Why we hold this** — the medical statement and the health history declared on the competition entry form are processed on the basis of your **explicit consent**, given when you choose to complete and submit the form. You can withdraw that consent at any time by contacting us at the address in Section 11, although an organizer may then be unable to admit you to the competition under AIDA rules.

### 2.11 Safety and Medical Records During an Event

Freediving competitions are safety-critical, and AIDA rules require certain medical events to be recorded and acted upon. The App therefore stores:

- **Risk marking** — a safety flag (none / yellow / orange / red) that the Organizer, Main Judge, Judge or Safety staff may set on an athlete before a performance, so that safety divers and judges are prepared. The flag is visible to event staff in the App and on a paired Apple Watch, and is stored with the athlete’s event entry.
- **Black-out follow-up records** — if an athlete has a black-out or is marked at elevated risk, the Organizer or Main Judge records a follow-up decision (“cleared” or “medical re-examination required”), an optional medical note, who decided, and when. This record is shown again at check-in on later days of the same event.
- **Medical statement revocations** — if a re-examination is required, the Organizer or Main Judge may revoke your medical statement. We store the revocation time, who revoked it and the reason given, both on the event submission and on the copy saved to your profile, and we notify you by push notification. The reason itself is not included in the notification. A revocation can be undone by the same roles.

**Why we hold this** — to run the event safely and to comply with AIDA competition rules. Because this is health information, we process it as necessary to protect the vital interests of athletes and safety staff in a safety-critical sport, and because it is required by the competition rules you agree to when you enter an AIDA event. Access is restricted to the event’s Organizer and Main Judge, except for risk marking, which safety-relevant staff can also see. These records are held as part of the event record and are deleted when the event is deleted.

### 2.12 Announcements and Staff Messages

The App includes an event Board (announcements written by the Organizer or Main Judge and readable by everyone in the event) and Dispatch (messages sent by event staff to selected staff members). For each message we store the text, the sender’s name and email address, the time, and — for Dispatch — the list of recipient email addresses. When a message is sent as a push notification, its text is passed to OneSignal exactly as written and is not translated. Messages are part of the event and are deleted when the event is deleted.

### 2.13 Exclusion Records

If an Organizer removes you from an event, the App keeps a record of that exclusion so that the App’s automatic athlete-matching does not add you back and silently undo the Organizer’s decision. The record contains your email address, your AIDA athlete ID, a normalized form of your name, who excluded you, any reason the Organizer entered, and the time. It is kept for the event even after you are no longer a member, and it is not removed on a schedule. An Organizer can override it by issuing you a new personal invite code. See Section 5.

### 2.14 Apple Watch Companion

The App includes an Apple Watch companion that shows the start list and, on Apple Watch Ultra, a dive screen with depth, dive time and water temperature while you are submerged. The watch asks for Motion & Fitness permission for this. **Depth, water temperature and dive time are displayed on the watch only** — they are not sent to the phone, to our servers, to AIDA, or to anyone else, and they are not stored. Data flows one way: the phone sends the event name, your role, your name and the start list (including safety risk markings) to the watch.

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
  * **Automatic notifications** triggered by event state (schedule changes / OT delays affecting specific athletes; check-in deadline reminders sent to athletes who have not yet checked in; protest activity — filed, awaiting athlete signature, decided); Board announcements posted by the Organizer or Main Judge; Dispatch messages addressed to you by event staff; missing-document reminders; and notification that your medical statement has been revoked. Board and Dispatch text is sent as written and is not translated.
  * Notification text is localized to the recipient’s app language, except for Board and Dispatch message bodies
- Record safety and medical information required to run the event under AIDA rules (see Section 2.11)
- Keep a record of participants an Organizer has removed from an event, so that automatic athlete matching does not re-add them (see Section 2.13)
- Enforce that one account is signed in on one device at a time


We do **not** use your information for advertising, marketing, or sale to third parties.

---


## 4. Data Sharing

### 4.1 With AIDA International

When an event organizer configures AIDA integration with their API token:

- We **read** event days, start lists, and athlete information from AIDA International
- We **submit** judge results (athlete performance, cards, penalties, remarks) back to AIDA International


This sharing is essential for the App’s core function and is initiated by the event organizer.

Separately, when an athlete uses the **“Find me on AIDA”** feature, the App sends the name text you type to AIDA International’s public athlete-search service in order to retrieve matching athlete profiles. Only the search text is sent; no account credentials or other personal data are included.

The App also requests athletes’ public AIDA profile and results pages when a profile is opened in the App. Only the athlete’s public AIDA UUID is sent.

### 4.2 Within Events

Event participants (organizers, main judges, judges, staff) can see:

- Names, profile pictures, and roles of other participants in the same event
- Athlete information for that event
- Real-time updates of judge results
- Activity logs (shown in the App to Organizers and Main Judges; see Section 2.6)


Athletes who have linked their account can see:

- Start lists for events they appear in
- Their own competition results


Information is scoped to the event — users in one event cannot see data from another event they don’t belong to. Athletes do not see other athletes’ personal account information.

### 4.3 Third-Party Service Providers

We use the following service providers to operate the App:

- **Supabase** ([supabase.com](https://supabase.com)) — backend authentication, database, real-time synchronization, and file storage (profile pictures, generated protest form PDFs, and submitted competition documents including medical statements and signatures)
- **Apple — Sign in with Apple** — if you choose to sign in with Apple, Apple authenticates you and shares your name and email (or a private relay email) with us. See Apple's privacy policy at [apple.com/legal/privacy](https://www.apple.com/legal/privacy/).
- **Google — Google Sign-In** — if you choose to sign in with Google, Google authenticates you and shares your name and email with us. See Google's privacy policy at [policies.google.com/privacy](https://policies.google.com/privacy)
- **OneSignal** ([onesignal.com](https://onesignal.com)) — delivery of push notifications to mobile devices. When a notification is sent, the destination Subscription ID, the notification title, and the notification body pass through OneSignal’s infrastructure. For Board announcements and Dispatch messages the body is text written by event staff and is passed through exactly as written (see Section 2.12). OneSignal may also collect device-level metadata (device model, OS version, language, timezone, country, IP address) for delivery optimization. See OneSignal’s privacy policy at [onesignal.com/privacy](https://onesignal.com/privacy_policy). OneSignal in turn forwards the notification payload to platform-level push services — Apple Push Notification service (APNs) for iOS and Firebase Cloud Messaging (FCM) for Android — for final delivery to the device.
- **AIDA International** ([aidainternational.org](https://www.aidainternational.org)) — official source of competition data
- **Apple App Store** and **Google Play Services** — app distribution and crash reporting
- **Sentry** ([sentry.io](https://sentry.io)) — automated error and crash diagnostics. When the App encounters a crash or an unexpected error, a diagnostic report is sent containing the type of error, the code location where it occurred, the app version and build number, the device model, and the operating system version. This reporting is deliberately configured for **data minimisation**: it does **not** send your IP address or device identifiers, does **not** capture screenshots or screen contents, does **not** include request bodies, authentication tokens, or your account information, and does **not** track usage or behaviour. Before a report is sent, the App removes the user and request context and masks email addresses and long encoded values (such as captured signature images) in the report’s message and breadcrumbs; if that processing fails, the report is discarded rather than sent. The same masking is applied to the exception's type and message. Reports are used solely to find and fix defects, and are especially important for the safety-related features of the App. Sentry processes this data in the United States; see Sentry's privacy policy at [sentry.io/privacy](https://sentry.io/privacy/).


These providers process data on our behalf and are bound by their own privacy policies.

### 4.4 Legal Requirements

We may disclose information if required by law, court order, or to protect the rights, property, or safety of users.

### 4.5 Shared Sign-In Across ELfreediving Apps

Apnea Comp uses a shared sign-in system operated by ELfreediving. A single account — whether created with email/password or through Apple or Google sign-in — can be used to sign in to other ELfreediving apps. For sign-in purposes, your **account credentials and basic profile** (email, display name, and profile picture) are shared across these apps. Your **Apnea Comp competition data** (events, start lists, results, documents, and protests) is scoped to Apnea Comp and is **not** shared with other apps.

---


## 5. Data Retention

- **Account data** — retained while your account exists. Deleting your account removes your sign-in credentials and your profile (display name, profile picture, linked AIDA athlete UUID, push subscription and language setting). Records that form part of an event’s official competition record — your event membership, results, check-in, activity-log entries, protests and submitted documents — are identified by the email address you used and are not removed by account deletion; they are removed on their own schedule (event deletion, or the document retention periods below). If you want those removed sooner, contact us at the address in Section 11.
- **Event data** (athletes, results, check-in status, protests, documents, announcements and staff messages, black-out follow-up records) — automatically deleted when the event organizer deletes the event.
- **Activity logs and the judging audit** — kept for the lifetime of the event record. They are not linked to the event by a database constraint, so deleting an event does not remove them automatically; contact us at the address in Section 11 if you need them removed.
- **Exclusion records** — if an Organizer removes you from an event, we keep a record of that exclusion (your email address, your AIDA athlete ID and a name key, who removed you and any reason given) so that automatic re-registration does not undo the Organizer’s decision. This record is retained indefinitely and can only be overridden by a new personal invite code issued by that Organizer.
- **Bulk download archives** — when an Organizer or Main Judge downloads all of an event’s documents or protest forms as a ZIP, the archive is written to our file storage and shared through a link that expires after 10 minutes. Document archives are deleted after one day; protest archives are deleted after 30 days.
- **Protest data** (reason, signatures, decisions) — held as part of the event and deleted together with the event when the organizer deletes it. The generated protest PDF stored in our file storage is removed when an individual protest is deleted, and in all cases is **automatically deleted 30 days after it is generated**. The protest record itself — including the reason, the decision and the stored signatures — is not time-limited and remains until the event is deleted, after the PDF has gone.
- **Document submissions** (competition entry, image rights, liability, and event-submitted medical) — kept as part of the event and **automatically deleted 15 days after the event ends**. A medical statement you save to your own profile is retained for its one-year validity and can be withdrawn at any time.
- **OneSignal Subscription ID** — cleared when you sign out of the App, when a different account signs in on the same device, or when OneSignal next reports the subscription as no longer reachable (for example after the App is uninstalled or notification permission is withdrawn). Until then the identifier remains stored on your profile.
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

- **Organizer / Main Judge** — can manage events, members, and competition data; view activity logs; review submitted documents; record black-out follow-up decisions; send manual push notifications. An Organizer may join as an **Observer**, which hides them from the event’s member list but grants the same permissions.
- **Judge** — can view and submit competition results, set risk markings, and view protests
- **Safety** — can view event data and set risk markings
- **Photo** — can view the start list and record which athletes they are assigned to photograph
- **Staff** — can view event data
- **Athlete** — read-only access to start lists, their own competition results, their own submitted documents and protests concerning them
- Permissions are scoped per-event; a judge in one event has no access to another


### AIDA API Token Protection

- AIDA API tokens (used to sync with AIDA International) are held in a separate, locked database table that no application role can read or write directly: all access is denied by default and granted only through restricted server-side functions. They are encrypted at rest by our infrastructure provider along with all other data.
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

The App is intended for event organizers, judges, staff and athletes taking part in AIDA-sanctioned competitions. Accounts are intended for users aged 16 and over. Where an athlete taking part in a competition is under the age of majority in their country, the competition entry, image rights, liability and medical documents must be completed and signed by a parent or legal guardian, in line with AIDA’s competition rules; the App records the date of birth entered on the competition entry form and the signature provided. We do not knowingly collect personal information from children under 13 without parental consent.

If you believe a child’s information has been provided without the necessary consent, contact us at the address in Section 11 and we will delete it.

---


## 8. Your Rights

You have the right to:

- **Access** the personal information we hold about you
- **Correct** inaccurate information through the App’s profile settings
- **Delete** your account and associated data
- **Withdraw consent** by uninstalling the App and requesting account deletion
- **Disable notifications** through your device’s system settings. Your device then stops receiving notifications immediately. The subscription identifier stored on your account is cleared when you sign out of the App, when another account signs in on the same device, or when our push provider next reports the subscription as no longer reachable.
- **Export** your data (contact us for assistance)


Deleting your account in the App removes your sign-in and profile immediately. Competition records that identify you by email address are removed on the schedules described in Section 5; contact us if you need them removed sooner.

To exercise these rights, contact us using the information in Section 11.

---


## 9. International Data Transfers

The App may process and store data in regions where our service providers operate. Supabase data is stored in South Korea (Seoul region). Push notifications are routed through OneSignal, which operates globally and may process notification metadata in the United States and other regions where their infrastructure is located. OneSignal in turn forwards notifications through Apple Push Notification service (APNs) and Firebase Cloud Messaging (FCM), which also operate globally. Error and crash diagnostics are processed by Sentry in the United States; these reports are configured not to carry personal information (see Section 4.3). By using the App, you consent to your data being transferred to and processed in these regions.

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
