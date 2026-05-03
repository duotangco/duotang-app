# Security Policy

## Reporting a vulnerability

To report a security vulnerability in Duotang, email **human@duotang.co**. Please do not file security issues in public GitHub Issues — that gives attackers a head start before a fix is available.

Include as much detail as you can: steps to reproduce, affected version, and any proof-of-concept. We'll acknowledge receipt within 48 hours and aim to have a fix in review within 7 days for critical issues.

## Scope

Duotang is a Chrome extension (Manifest V3). Relevant areas include:

- Content script injection and isolation
- Message passing between content scripts and the background service worker
- Storage handling (`chrome.storage.local` and `chrome.storage.session`)
- Declarative Net Request rules (used for Peek's header stripping)
- Any feature that makes network requests on the user's behalf

## What Duotang can and cannot access

- **Can access:** Page content on `http://` and `https://` URLs where the user has the extension active. Downloads metadata. Tabs and windows (with `tabs` permission).
- **Cannot access:** Passwords, payment information, or any data handled by the browser's built-in password manager. Content on `chrome://`, `chrome-extension://`, or `file://` pages. Other extensions' data.
- **Does not store remotely:** All user data stays in `chrome.storage.local` on the user's device. No remote backend, no cloud sync.

## Supported versions

Only the latest version published to the Chrome Web Store is supported. We do not backport security fixes to older versions.
