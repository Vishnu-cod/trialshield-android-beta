# TrialShield privacy information — v0.9-beta

Last updated: 23 November 2026.

## Local records
TrialShield stores subscriptions/trials that you add: service, expected amount,
currency, billing cycle, next estimated charge date, optional account URL and
user-confirmed cancellation status. These records are stored in the Android
app's local database, with a rollback JSON copy.

## Optional notification discovery
**Off by default.** Only after a prominent in-app explanation, your consent,
and a separate Android system grant can TrialShield receive notifications
from other apps. Android notification access may expose ALL future app
notification content, including personal messages, financial details and
one-time verification codes.

The app examines new notification text locally for recognized subscription
services, billing wording and possible renewal details. Obvious verification-
code messages are rejected. Candidate summaries alone are saved locally:
service, amount/currency, billing cycle, possible next charge date, source
application ID, detection time and confidence label. **Original notification
text, passwords, bank account details and verification codes are not saved
or uploaded by the discovery feature.** It cannot inspect old notifications.

The feature can miss subscriptions or produce false positives. Candidates are
never silently added to tracked trials. You must review and save them.
Dismissed candidates are suppressed from repeated notifications.

You can turn off local discovery in TrialShield, clear its stored findings and
dismissals, or revoke notification access separately in Android Settings.
**Turning discovery off in the app does not revoke the Android permission.**
Deleting discovery data does not delete subscriptions you already saved.

## Local-only and cloud
TrialShield does not use a developer-operated server, analytics SDK,
Gmail account access, banking connector or cloud synchronization.
"Connected Mode" is a future concept and is disabled in this release.
If connected services are added later, new explicit consent and a privacy
policy update will be required.

## Imports, exports, provider websites
Sharing or pasting text processes it locally, and requires review before Save.
Exported backup JSON files are UNENCRYPTED and saved to a user-chosen location;
protect and delete your copies separately. Opening provider account pages
launches external HTTPS websites governed by their own privacy notices.
TrialShield cannot cancel subscriptions or prevent charges directly.

## Operating-system permissions
Notifications and exact-alarm access are used to schedule charge reminders;
reboot broadcasts restore scheduled reminders. Android may delay or suppress
these alerts. TrialShield never guarantees actual delivery or billing status.

To delete tracked data, use in-app deletion. Clearing app storage or
uninstalling removes local data but not already-exported backups.

For support or privacy concerns, contact the GitHub project owner via the
repository's Issues page without including private records or personal
credentials. A dedicated support contact is still needed before a broader
store launch.
