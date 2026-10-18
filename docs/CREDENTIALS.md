# Documentation generator credentials

The generator reads `COMPOSIO_API_KEY`, `GOOGLE_SHEETS_ACCESS_TOKEN`, and
`GOOGLE_SHEET_ID` from its process environment. If your backend also requires a
session cookie, set `COMPOSIO_AUTH_TOKEN`. Never put these values in source code.

Use the hosting/CI secret store or export variables in your local shell before
running the generator. `docs/.env.example` documents names only; the generator
does not automatically load a `.env` file. Use read-only Google Sheets access for
the intended spreadsheet.

Previously committed OAuth tokens and session cookies remain in Git history.
Their owners should revoke any still-valid tokens/grants and issue fresh values.
Do not copy sample tokens from old documentation into a live configuration.

Generator errors intentionally avoid printing Axios error objects, which can
contain request headers and credentials. Diagnose access failures in the provider
console without logging raw tokens.
