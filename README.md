# EnshroudedVermillion

Signed setup + over-the-network updates for the **Shinra CC** modded Enshrouded client.

This is the public update channel. The actual source is private; this repository hosts only
this README, a CHANGELOG, and — on each release `vN` — the **Authenticode-signed** setup exe plus
its update manifest (`enshroudedVermillion-update.json`) and detached signature.

## For players (Chris)

You don't need anything here directly. Run the **EnshroudedVermillion setup** that scook gave you:

1. Run `EnshroudedVermillionSetup.exe`.
2. Read what it will do and click **I agree**.
3. It configures your PC to match scook's modded client automatically (nothing to hand-edit), then
   shows the **launcher**.
4. In the launcher you'll see the server address + port to search for, your join password, and a
   **Play** button.

A small tray app keeps itself up to date from this channel and tells you when scook ships a change —
click **Update** and it re-applies the latest client. You can set it to run quietly in the tray so
it's never in your way.

Everything is signed by **Shinra CC** (code-signing certificate thumbprint
`894D9D9C322718065D6B116545B357D01C2A8E57`), which the setup trusts on your PC so nothing shows up as
an "unknown publisher."

## How updates work

The tray app reads [`enshroudedVermillion-update.json`](enshroudedVermillion-update.json) from the
`main` branch. When its `version` is newer than what you have, it offers the update, downloads the
signed setup from the matching release, verifies the SHA-256 and the signature, and runs it.
