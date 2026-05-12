# Changelog

## v0.1.5

- Places SGManager at the upper-left work area on startup to reduce Chrome overlap.
- Minimizes SGManager during click-all runs and restores it before showing completion or error results.
- Opens Chrome in the right half of the work area and corrects the window bounds after launch.
- Updates SGManager app and Windows executable versions to 0.1.5.

## v0.1.4

- Shows `[SG] ING (작업중)` in the Chrome title while full automation is running.
- Retries the full automation button click once after 5 seconds when Chrome remains open and idle.
- Updates SGManager app and Windows executable versions to 0.1.4.

## v0.1.3

- Closes Chrome through WM_CLOSE during token capture instead of force-killing it.
- Keeps STOVE launcher fallback and attendance-game process cleanup on `taskkill /F`.
- Updates SGManager app and Windows executable versions to 0.1.3.

## v0.1.2

- Adds public release channel configuration for in-app update checks.
- Adds click-all controls for selecting the starting account and stopping runs.
- Keeps local capture artifacts out of source history.

## v0.1.1

- Adds an in-app update check button and startup update check.
- Downloads new `SGManager.exe` releases to the local updates folder.
- Keeps replacement manual so the running app is not overwritten automatically.

## v0.1.0

- Initial public release channel for SGManager.
- Includes `SGManager.exe` built from the private development repository.
