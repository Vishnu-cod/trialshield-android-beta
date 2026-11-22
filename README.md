# TrialShield — Android preview

TrialShield helps you record free trials and planned subscription charges, see estimated monthly costs, and receive Android reminders before expected billing dates.

**Current release: v0.8-rc (testing preview).** This is a debug-signed Android APK shared directly through GitHub, **not a Google Play app or a production-ready payment protection service**.

## Download and install

Find **TrialShield-v0.8-rc-debug.apk** under the latest GitHub release's **Assets** section. See [INSTALL.md](INSTALL.md) for safe installation steps.

## Features available

- Add, edit, and remove tracked trials and subscription entries.
- Receive alerts scheduled for approximately **72 hours, 24 hours, and 2 hours** before a charge date, subject to Android notification, exact-alarm, and battery rules. A late-added trial may receive an urgent reminder.
- Review your estimated recurring cost, shown separately for INR, USD, EUR and GBP.
- Choose weekly, monthly, quarterly, or annual billing periods.
- Import a possible subscription from pasted or shared text, then **review and save it yourself**.
- Open 20 provider-owned cancellation account pages or guides (or a link you enter).
- Use a home-screen widget, a date picker, and a local JSON backup/restore feature.
- Mark an entry canceled only **after** the billing provider confirms cancellation.

## Important limitations

**TrialShield cannot automatically cancel subscriptions, stop charges, verify billing, or access your bank account.** You must cancel with the provider, app store, or reseller that actually bills you.

Android may delay or suppress notifications, especially during power saving, Doze, or after force-stopping the app. This beta has not completed multi-day, multi-device reliability testing. **Keep a separate reminder for important payments.**

TrialShield does **not** automatically read Gmail or scan SMS. Text imports require sharing or pasting, and confirmation. Backups are unencrypted; protect exported files.

## Privacy

Trial data is stored in the app's private Android storage. There is no developer-operated server or analytics service in this beta. See [PRIVACY.md](PRIVACY.md).

## Test feedback

When reporting a problem, include your Android version, phone model, the TrialShield version, and the steps to reproduce the issue. **Never share passwords, card numbers, private subscription emails, or personal billing information in a public GitHub issue.**

## Source code

This repository is intended for **APK preview distribution**. The source code has not been publicly licensed or published in this release. No open-source license is being granted through this repository.

## Version and compatibility

- Version: **0.8-rc** (version code 8)
- Application ID: `com.example.trialshield` (development ID)
- Android: **8.0+** (API 26 minimum)
- Package: debug-signed APK; no automatic in-app updater
