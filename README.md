# Miqat Reminder — Android 15

This repository holds the build automation for **Miqat Reminder v0.3.0**, targeting Android 15 with Arabic/English support. It is currently **not** a published or verified APK release.

## Current build blocker

The CI workflow exists at `.github/workflows/miqat-build.yml`, but the repository does not yet contain `Miqat-Reminder-v0.3.0-PUBLIC-SOURCE.zip`. The first workflow run stopped at source validation, *before Android compilation*. Do not report this as a successful build.

## Complete the existing project build (do not recreate the app)

1. Open [Upload files to main](https://github.com/megypt9000-jpg/miqat-reminder-android/upload/main).
2. Upload the **exact sanitized** `Miqat-Reminder-v0.3.0-PUBLIC-SOURCE.zip` archive to the repository root without renaming or extracting it.
3. Commit the uploaded ZIP. This automatically triggers [GitHub Actions](https://github.com/megypt9000-jpg/miqat-reminder-android/actions).
4. When the **Miqat Android 15 APK** build succeeds, download the `Miqat-v0.3.0-Android15-DEBUG` build artifact. Verify Android 15 alarms, snooze, checklist, keyboard insets and upgrade behavior on an actual device before labeling a final release.

## Safety / upgrade compatibility

This repository is public: **do not upload** the full private `ALL-FEATURES-SOURCE.zip` archive, private signing keystores, passwords or other secrets. Only upload the sanitized `PUBLIC-SOURCE.zip`.

The GitHub workflow currently signs with a new debug certificate. That APK can install on a clean device, but **cannot update an existing Miqat installation signed by a different key** without uninstalling the old app. Uninstalling may lose saved local reminders. A safe in-place update requires matching the original signing certificate through encrypted GitHub secrets; never commit the signing key into a public repository.
