# TrialShield Privacy — v0.10 experimental preview

Last updated: 23 November 2026.

## Tracked subscriptions

TrialShield stores user-added free-trial/subscription entries, amounts,
billing cycles, expected dates, provider links and confirmed-cancellation
status in its private on-device database. It keeps a local rollback copy.
No developer-operated account service, cloud sync or analytics network
receives those records in this version.

## User-selected bank CSV statements

In the new **Gmail & Bank Discovery** panel, you may choose a bank CSV via
Android's document picker. TrialShield reads it on the phone only, with a
size limit, and checks for repeated debits to known services. **The raw file,
account numbers, transaction descriptions, account identity and credentials
are NOT uploaded or persisted by TrialShield**. A few derived candidate
summaries remain in app memory until you leave or clear the session.
Nothing is added to subscription tracking until you review and save it.
Past debits are NOT proof of an active subscription or its next charge.

This is NOT a live bank connection, and we have no access to UPI AutoPay
mandate history, bank accounts, net-banking passwords, PINs or OTPs.

## Gmail OAuth code (disabled for end users)

The app contains an Android Google AuthorizationClient integration and
a limited `gmail.readonly` Gmail API scanning module, but that connector
is **not activated in this release**. It does NOT connect to or read your
Gmail account today. Public access would need a verified Google Cloud
project, a registered Android client, approved restricted OAuth scope
and any applicable security assessment.

After approval, users would be asked for explicit authorization before a
one-time user-invoked scan of up to 20 recent matching Gmail messages.
Only subjects/snippets would be processed locally, to derive suggested
subscription records requiring review. The implementation does not save
Gmail access tokens, email content or message IDs in the app database;
no TrialShield backend receives Gmail messages. Revoking Google permission
is supported by the connector when it is enabled.

TrialShield's use of Google Workspace API data, when enabled, will adhere
to the Google API Services User Data Policy, including its Limited Use
requirements. This is a development disclosure, not a statement that
Google has approved the unactivated app.

## Notification discovery (optional, separate)

Off by default. If you consent in-app AND grant Android special notification
access, the app may see all future notifications, including sensitive
personal messages and security codes. It scans locally for likely
subscription signals, rejects obvious security-code text, and saves only
derived candidate summaries; raw message text is discarded. Revoke special
access in Android Settings separately from turning the in-app feature off.
Use Delete discovery data to clear associated local findings.

## Backups, outside websites, alerts

Users may export/restore unencrypted local JSON backups through Android's
file picker. Keep backups private. Opening cancellation pages launches
third-party HTTPS sites with their own privacy notices.

Android may delay reminder alerts. TrialShield cannot verify payment, stop
charges, cancel providers' subscriptions, or guarantee reminders. The app
does not require banking credentials or payment cards.

## Controls and contact

Edit/delete tracked subscriptions in-app. Delete discovery findings
separately and clear Gmail session results using the relevant controls
(when enabled); revoke any future Gmail grant using Disconnect or Google
Account settings. Clearing app storage/uninstalling deletes private app
data, not separately exported backup files.

For project or privacy concerns, open an issue at
https://github.com/Vishnu-cod/trialshield-android-beta
without posting private email, banking statements, or account credentials.
The owner must publish a dedicated verified support email before a
production Play Store listing.
