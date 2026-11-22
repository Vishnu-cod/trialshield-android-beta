# TrialShield Security

This is a debug-signed experimental APK. Do not bypass Play Protect or
Android's restrictions when installing or granting special notification access.
Do not provide card numbers, passwords, UPI PINs, OTPs or other credentials.

- Bank CSV files are processed locally. No raw statement is saved in the app.
- Gmail API code is present but OAuth is disabled pending official verification.
- The enabled Gmail flow (when approved) would use a temporary OAuth token
  only in memory; it is not stored, and no TrialShield server exists.
- Notification discovery is opt-in and separate from Gmail/bank functions.
- Exported JSON backups are unencrypted.

Please report issues without personal or banking records in public GitHub Issues.
