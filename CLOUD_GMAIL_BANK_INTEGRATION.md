# TrialShield — Gmail and Indian Bank Discovery Integration Plan

Last reviewed: 23 November 2026

## Exactly what works in v0.10-cloud-foundation

* The app now has an optional **bank CSV statement importer**, using Android's user-controlled document picker. Parsing and recurring-debit detection happen on the device. It never uploads the statement or stores account numbers. It requires at least two similar debits to a recognized provider, and still asks the user to provide the **exact future payment date and time**. This is NOT a live bank connection.
* A `GmailCloudDiscovery` REST scanner and Google Play Services authorization UI are implemented in source and guarded behind `BuildConfig.GMAIL_OAUTH_READY = false` for safety. The scanner would search up to 20 recent matching message snippets with the user-granted `gmail.readonly` scope. No raw email or access token is persisted; users can revoke authorization. This **is not activated for end users** until Google Cloud setup and policy approval.
* Live RBI Account Aggregator, banking credentials, automatic UPI mandate inventory, Gmail background monitoring, cross-device synchronization and any server are **not active**.

## Gmail connector activation — owner action required

1. Create or use an owner-controlled Google Cloud project at https://console.cloud.google.com/ (avoid sharing passwords or API secrets).
2. Enable the Gmail API in that project.
3. Configure OAuth consent, app branding, support email, privacy policy HTTPS URL and only the required Gmail read-only scope. Google classifies `https://www.googleapis.com/auth/gmail.readonly` as **Restricted**.
4. Register an **Android** OAuth client for TrialShield's final app package ID and **SHA-1 signing certificate**. This is currently a development package `com.example.trialshield`, not a final brand identity. Publishable releases use a separately controlled production signing identity.
5. Add tester accounts for unverified development where allowed; meet Google's app verification and restricted-scope requirements before inviting general users. Additional security assessment may apply, especially if restricted data goes to a server.
6. Verify the Limited Use Google User Data Policy privacy disclosure.
7. Then and only then change `buildConfigField("boolean", "GMAIL_OAUTH_READY", "true")` in the build config and test OAuth, query reliability, denied scopes, revocation and Play policy before distributing.
8. Auth tokens are ephemeral and kept only in app memory; the current feature is **user-invoked**, not automatic scheduled cloud scanning. A consented and compliant backend would be a separate project.

Relevant official references:
- Gmail scopes: https://developers.google.com/workspace/gmail/api/auth/scopes
- Gmail user data policy: https://developers.google.com/workspace/workspace-api-user-data-developer-policy
- Google Android authorization: https://developers.google.com/android/reference/com/google/android/gms/auth/api/identity/AuthorizationClient
- OAuth clients for Android: https://developers.google.com/workspace/guides/create-credentials

## Live bank integration — partner required

India's RBI Account Aggregator (AA) system is consent-based. An eligible/regulated Financial Information User (FIU) or compliant provider partnership is needed to receive data via the network. A general consumer APK cannot legitimately read arbitrary users' bank transactions or UPI AutoPay mandates just by asking for their bank password.

We need a contracted partner, approved intended use, user consent, identity and data security controls, revocation and audit trails, and a secure server/provider integration. Do NOT build bank password, OTP, UPI PIN or screen-scraping flows. A real UPI AutoPay mandate integration is different from statement analysis and requires the appropriate payment-system access.

References:
- Indian government AA overview: https://financialservices.gov.in/account-aggregator-framework
- RBI AA 2025 directions: https://www.rbi.org.in/Scripts/BS_ViewMasDirections.aspx?id=12936
- NPCI MyUPI consumer portal: https://www.npci.org.in/product/myupi.html

## Bank CSV importer privacy design

- File picker returns a temporary readable URI. The app opens it and **does not take persistent URI access**.
- Max about 1.5 million characters and 4,000 rows. Larger files rejected.
- Needs Date + Description/Narration + separate Debit; Amount-only exports require DR/CR transaction type, so positive incoming transfers are not confused with charges.
- Considers only recognized provider names and at least two debit records with similar amounts and typical recurring intervals.
- Only local candidates are retained in in-memory Compose state until the user leaves or clears the screen; the statement is not persisted.
- App does **not** infer exact future charge time from a bank statement.
- The user must review and manually save. Deduplication with existing TrialShield records still requires human review.

## Future backend/API integration design (not deployed)

`POST /v1/connections/{provider}/start`: short-lived authorization start session, state and nonce.
`POST /v1/connections/{provider}/callback`: server-side code exchange; never receive bank passwords.
`GET /v1/discoveries`: only user-scoped, consented candidate summaries and confidence/provenance.
`DELETE /v1/connections/{provider}`: revoke server-side tokens, delete raw linked information, preserve manual entries if requested.

Required: authenticated user session, CSRF/state+PKCE, encrypted per-user tokens in a secrets vault, least-privilege provider access, consent timestamps/scope, automatic expiry, deletion, rate limits, vulnerability reporting, audit logs without private data, migration and privacy review. Do not deploy or claim this API exists until real partner accounts and a security review are available.

## Release restrictions

Keep `GMAIL_OAUTH_READY=false` in the publicly distributed APK until verified. Do not silently enable scanning or submit any banking/credential requests to third parties. We can still offer the local statement importer for free.
