# Jee OneShot OS 3.1.5 APK build fix

The previous workflow failed because it called `require.resolve('@capacitor/android')`. The Android platform package is consumed by the Capacitor CLI as a native platform package and may not expose a Node.js entry point. The workflow now checks that `node_modules/@capacitor/android/package.json` exists and uses Node resolution only for `@capacitor/core` and `@capacitor/cli`.

The app data/UI scope is preserved: 54 ordered one-shots, chapter names only (no actual YouTube video titles shown), one shot per calendar day including Sundays, revision, no tests, no duration/speed UI, and external YouTube links.

This archive contains the corrected GitHub Actions workflow. An APK is not included; GitHub Actions must run to compile it.
