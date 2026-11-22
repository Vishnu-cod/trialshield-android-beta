# TrialShield v0.10 — Cloud Discovery Foundation

**Status:** Experimental preview. The Gmail connector is implemented but
**disabled** in this APK until Google Cloud OAuth registration and
restricted-scope verification are complete. A real bank account connector
is NOT yet available.

## Added
- A new **Gmail & Bank Discovery** panel.
- **Bank CSV import** through the Android system document picker. Users select
  their statement. On-device analysis finds possible recurring debits to
  recognized merchants, without retaining the raw statement.
- Conservative bank matching: Date, Description/Narration, Debit columns
  (or Amount + DR/CR); repeated debit amounts within approximately 10%
  and weekly/monthly/quarterly/annual timing intervals.
- Bank discoveries need two or more similar past debits and are only
  **possible**, not confirmed subscriptions. Exact future billing time is
  unknown, so the Save button stays disabled until manually reviewed.
- Gmail authorization client implemented with Google Play services and
  Google's `gmail.readonly` OAuth scope; one-time Gmail API query code with
  a 20-message cap and local snippet parsing.
- Consent dialog, session-only results, and a Gmail authorization revocation
  action. The Gmail connection is gated OFF in this preview, not a live
  inbox scanner. No credentials requested or stored.
- Owner setup guide covering verified Google OAuth and a lawful Indian
  Account Aggregator/Financial Information User partnership.
- No third-party bank passwords, UPI PINs, OTP capture or live bank access.

## QA evidence
- 43 automated tests passed.
- Android debug APK build and lint succeeded.
- Emulator: imported a synthetic bank CSV, proposed a Netflix ₹649/month
  candidate after three historical debits; the Add Trial review showed
  the candidate, and Save stayed disabled because the future date was blank.
- No trial was created without explicit human confirmation.
- Gmail OAuth could not be tested against an actual Gmail account because
  a verified Google Cloud OAuth client has not been configured.

## Risks and limitations
- No cloud backend, scheduled cloud sync, live account connections, automatic
  payment cancellation, or confirmed charges.
- The existing v0.9 notification discovery remains optional.
- Gmail API access (if activated later) uses Internet permission and requires
  Google's OAuth app verification for restricted scopes.
- Bank CSV exports vary. Statement analysis can miss subscriptions and
  can falsely suggest recurring purchases. Never treat these as guaranteed.
- Android may delay reminders. Use an independent reminder for important bills.
- This preview APK is debug-signed. Do not bypass Play Protect or Android
  restricted-settings warnings to install it.

Read `CLOUD_GMAIL_BANK_INTEGRATION.md` and `PRIVACY.md`.
