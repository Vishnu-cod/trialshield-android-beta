# TrialShield v0.8-rc — Testing prerelease

**Release status:** Android testing preview. Mark this as a **GitHub prerelease** rather than a stable release.

### Included
- Improved dark theme contrast, first-use guidance, and prominent next-charge summary.
- Local trial tracking using Room, editing, deletion, and confirmed-cancellation state.
- Scheduled 72h/24h/2h reminders (and an urgent late-added-trial reminder).
- On-device text import from Android Share/paste with manual review.
- Currency-aware monthly estimates and billing-cycle options.
- 20 provider-owned account/cancellation guides.
- User-controlled, unencrypted JSON backup export and confirmed merge restore.
- Home-screen widget provider and local diagnostic reminder button.
- Proposed next-renewal date, subject to user confirmation.

### Validation completed
- Android package version: `0.8-rc` (`versionCode 8`).
- **22 automated tests passed** in development.
- Debug APK signature verified with Android's APK signer.
- Prior emulator tests covered import review, billing calculations, reminders, and trial edits.
- Installed successfully on a POCO X6 Pro during development; local database was preserved.

### Known issues / important disclosures
- Does **not** directly cancel subscriptions or stop payments.
- Reminder timing is not guaranteed under Android Doze, OEM battery restrictions, or disabled notification permissions; long-duration physical-device testing is incomplete.
- No automatic Gmail reading, billing API integration, 500-service directory, or in-app updates.
- Widget appearance/refresh on a range of devices remains unverified.
- This is a **debug-signed** preview. Do not enter sensitive payment details.
- Not yet published, signed for Google Play production, or approved by Google's review.

**If a serious install security warning appears, do not disable Android protections to proceed.**
