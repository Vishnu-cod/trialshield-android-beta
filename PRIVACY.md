# TrialShield Android preview — Privacy

Last updated: 23 November 2026.

TrialShield tracks subscription and free-trial information **you choose to enter**. Records (service, expected amount, currency, billing cycle, expected billing time, optional cancellation route, and cancellation confirmation) are stored in the app's private Android database. It may retain a local migration copy and delivery diagnostic timestamps.

- The current APK has **no developer-operated server, online account, ad network, or analytics SDK**.
- Import from text processes content locally. It cannot automatically access a Gmail inbox, and it never saves an imported subscription without confirmation.
- The app opens provider-owned HTTPS pages using Android. Those websites have their own terms and privacy practices.
- Backups are saved **only when you export them**, using Android's document picker. JSON backups are **unencrypted** and should be kept secure.
- You may delete tracked records inside the app. Clearing app storage or uninstalling removes local records, but exported backups remain wherever you saved them.
- Notification and alarm permissions are used to remind you of expected charge dates. The app cannot verify or stop a provider's charge, and reminders may be delayed by Android.

To report a privacy concern, use the GitHub repository's Issues page and **do not post personal billing information**. The developer should add a dedicated support contact before broader distribution.
