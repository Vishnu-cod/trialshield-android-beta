# TrialShield Android — v0.10 Cloud Discovery Foundation

A free native Kotlin/Jetpack Compose beta for tracking trial deadlines,
estimated subscription costs and provider cancellation routes.

**v0.10 is an experimental beta, not a finished Gmail/bank cloud sync product.**

## What works

- Track and edit expected charges and get Android reminder notifications.
- Local subscription extraction from pasted/shared receipt text.
- Optional notification discovery (Android special permission; off by default).
- **NEW:** Import a bank CSV you choose and identify possible recurring
  merchant debits on the phone, without uploading the file.
- **NEW:** Review possible bank-derived subscriptions before adding them;
  exact future date/time must be supplied by a human.
- Multi-currency estimates, recurring cycles, 20 provider cancellation guides,
  widget and locally controlled unencrypted backup.

## What's built but not active yet

A Google AuthorizationClient + Gmail REST scanner is implemented and
compiled, but `GMAIL_OAUTH_READY=false` intentionally disables Gmail
connection until the owner registers a Google Cloud Android OAuth client,
enables Gmail API, completes restricted scope verification and updates
privacy controls. No Gmail scan is running in this public beta.

Real bank/UPI sync requires an approved Account Aggregator/FIU provider or
other compliant integration; it does not exist in this beta. We never ask
for a bank password or UPI PIN.

See [CLOUD_GMAIL_BANK_INTEGRATION.md](CLOUD_GMAIL_BANK_INTEGRATION.md)
for owner setup and detailed limitations.

## Test

Use Gradle tasks `:app:testDebugUnitTest :app:assembleDebug :app:lintDebug`.
43 tests passed during beta build. APK is a debug-signed build, min SDK 26,
versionCode 10, package `com.example.trialshield`.

Do not bypass Play Protect or Android restricted-settings warnings.
No automatic cancellation or guaranteed reminders. Keep a separate
reminder for important payments.
