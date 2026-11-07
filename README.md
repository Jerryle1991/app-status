# app-status

Public status files that my apps read to know whether they may still run.

## irl-chat-voice.json

| Field        | Meaning                                                                 |
|--------------|-------------------------------------------------------------------------|
| `enabled`    | `false` switches the app off on every phone (within an hour while reading, or at the next start). |
| `minVersion` | e.g. `"0.16.0"`: older versions show "update" and stop. `null` = no minimum. |
| `message`    | Optional text shown on the blocked screen (plain text, max 300 characters). |

The app keeps the last known state. If this file cannot be reached (offline,
404, repo renamed or deleted), the app keeps working for 14 days after its last
successful check and then stops until it can check again.

Keep this repo public, keep its name, and keep 2FA on the GitHub account:
whoever can change this file can switch the app off.

Changes reach phones within about 5 minutes (GitHub's cache) plus the app's
check interval (at start and every hour while reading).
