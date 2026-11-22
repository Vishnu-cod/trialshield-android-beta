# TrialShield — Android trial and subscription tracker

**Latest experimental beta: v0.9-beta.** Free download; not on Google Play.
This is a **debug-signed testing APK**, not a production-grade financial
protection service. GitHub release v0.8-rc remains available.

TrialShield helps you record expected subscription charges, review free-trial
deadlines and navigate provider-owned cancellation pages.

## Download
See **[Releases](https://github.com/Vishnu-cod/trialshield-android-beta/releases)**
for the latest **prerelease** and its Android APK. Check [INSTALL.md](INSTALL.md)
before sideloading.

## Features available
- Add, edit and delete tracked free trials and expected billing dates.
- Estimated per-currency recurring monthly costs (INR, USD, EUR, GBP).
- Android alarm scheduling for 72h, 24h, 2h before estimated charges
  (not guaranteed by Android), including a test reminder.
- Local text import from pasted/shared receipts, with review before saving.
- Browse 20 provider-owned cancellation account pages or guides.
- Back up local records in an **unencrypted** JSON file chosen by the user.
- Countdown widget (not validated across all Android launchers).
- **NEW in v0.9-beta: optional on-device notification discovery**. With
  explicit consent and Android notification-access permission, TrialShield
  checks only *future* notifications for known subscription services and
  renewal wording. The app queues potential matches as **Likely/Possible**,
  suppresses repeat candidates, and requires human review before tracking.
- Erase discovery findings separately from tracked subscriptions.

## IMPORTANT: Privacy and security
Notification access can expose **all future app notifications**, including
personal messages and security codes. It is **off by default**. If enabled,
TrialShield filters locally, rejects obvious verification messages, and
does not retain raw notification bodies. Only derived subscription candidate
information is stored in private Android app storage. **Nothing is uploaded
to a TrialShield server.** Users can disable discovery, erase findings and
revoke Android access separately in Settings. Read [PRIVACY.md](PRIVACY.md).

If Android or Play Protect gives a serious security warning or blocks this
sideloaded APK, **do not disable or bypass protection**. The optional feature
may be restricted on some phones. Manual tracking still works without it.

## Not implemented
- No automatic provider-side subscription cancellation, payment blocking,
  guaranteed alerts or confirmed billing data.
- No Gmail account scanning, Google Play billing inventory, bank/UPI
  connection, cloud sync, or server-side subscription discovery.
- Only a conservative 20-provider local catalog, not an exhaustive service
  directory. Automatic discovery can miss valid subscriptions.

**Do not depend on this experimental beta as your only reminder for real money.**

## Version
- v0.9-beta, versionCode 9, package `com.example.trialshield`
- Android 8.0+ (API 26 min)
- Updated in-place from the previous debug-signed 0.8 APK when signing
  identity matches; still export a backup before updating.

## Feedback
Open a GitHub issue describing the phone model, Android version and steps
to reproduce. **Never post login codes, financial statements or other
personal data in public GitHub issues.** Source code remains private and
is not licensed through this distribution repository.
