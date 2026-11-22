# TrialShield v0.10 Beta — Android APK installation

1. Download **TrialShield-v0.10-cloud-foundation-debug.apk** from the
   official [GitHub release](https://github.com/Vishnu-cod/trialshield-android-beta/releases)
   Assets section.
2. Install over an earlier compatible TrialShield debug-signed beta.
   Before updating, export your local trial backup (the JSON is unencrypted).
3. Do not bypass Android Play Protect or any serious security warning.
4. Open TrialShield -> **Gmail & Bank Discovery** -> **Explore connected discovery**.
5. To try **Bank CSV**, select a bank statement file you own with
   Date, Narration/Description, Debit (or Amount plus DR/CR) columns.
   Review possible subscriptions. A future charge date/time is required.
6. Gmail connection appears **disabled** until Google Cloud restricted-scope
   authorization is verified; do not try to enter Gmail credentials.
7. Bank CSV import does not connect to a bank or provide mandate access.

The Internet permission is included for the code-level Gmail OAuth/API
integration, but cloud account connection is NOT enabled in this beta.
No cloud backend or bank connector exists. The version is experimental;
do not rely on it for guaranteed reminders or preventing charges.
