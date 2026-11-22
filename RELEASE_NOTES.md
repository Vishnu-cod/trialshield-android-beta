# TrialShield v0.9-beta — Experimental Local Discovery

**GitHub prerelease only.** Not Google Play approved. The APK is debug-signed,
for testers, and should not be treated as a finished payment-protection app.

## New
- Optional **Smart Discovery**, OFF by default and enabled only after a
  prominent disclosure plus Android's special notification permission.
- On-device recognition of NEW notifications that combine a known service
  with subscription/renewal context and a price or recognizable charge date.
- Findings queue with source app, amount and date estimates, and
  **Likely** / **Possible** confidence labels.
- A review-and-add step that opens the editable trial dialog; no
  silent additions or automatic charges.
- Duplicate suppression for repeat notification matches.
- Disable local discovery, dismiss individual findings, and erase discovery
  records independently of already tracked trials.
- Clear "Connected Mode coming later" notice; no fake Gmail/bank connection.

## QA checks
- 31 unit tests passed, including 9 new matcher cases.
- Lint and debug APK compilation completed successfully.
- Emulator: opted-in listener recognized a simulated Netflix renewal,
  queued an estimate and did not store the original notification text.
- Emulator: repeat suppressed, an unclear Spotify reminder marked Possible.
- Emulator: trial was created only after review and explicit Save.
- Emulator: turning discovery off ignored new messages; deleting
  discovery history kept already tracked trials.
- The local emulator QA records and test access were cleared afterward.

## Important limitations
Android's special notification permission may be considered sensitive and
some devices/Play Protect may block sideloaded APKs using it. **Do not
bypass serious security warnings or restricted settings.**
The listener receives access to ALL future notifications when authorized,
even though TrialShield attempts to filter locally and does not
save raw bodies. Detection is not complete or foolproof.

No automatic canceling, Gmail integration, bank linkage, cloud sync,
real billing confirmation or guaranteed alerts. Long-duration testing and
policy/permissions review remain outstanding. Keep a separate reminder
for important charges.
