# Frequently Asked Questions

## Workspaces

**Does switching workspaces close my tabs?**
No. Switching workspaces never closes or reloads your tabs. In One Window mode, your current workspace's tabs move to a hidden background window and the new workspace's tabs move into view — all tabs remain live Chrome tab objects. In Multi-window mode, each open workspace has its own Chrome window and all windows stay open simultaneously. Your tabs are always where you left them.

**What happens to my scroll position, form data, and active sessions when I switch?**
They're preserved. Because tabs never close during a workspace switch, all in-memory tab state — scroll position, form data, video playback position, WebSocket connections, authenticated sessions, AI conversation context — survives the switch intact.

**What happens when I close a workspace's window?**
Duotang saves a snapshot of the workspace's tabs (URLs, titles, scroll positions, tab group membership). When you reopen the workspace, tabs are restored from that snapshot. Scroll position is recaptured and restored; transient state like form data and WebSocket connections is not, the same behavior as a browser restart.

**What's the difference between One Window mode and Multi-window mode?**
In One Window mode, all your workspaces share a single Chrome window. Switching shows the active workspace's tabs and hides the others (kept alive in a background window). In Multi-window mode, each open workspace gets its own Chrome window — you can have Work and Personal both open simultaneously and Alt+Tab between them like any other application. Multi-window is the default; One Window mode is opt-in from Settings.

**Is there a limit on tabs or workspaces?**
No. Duotang imposes no tab count limit and no workspace count limit, permanently and on the free tier.

**Do Chrome tab groups and pinned tabs survive workspace switches?**
Yes. Tab groups (colored label groups) and pinned tabs are preserved across workspace switches and survive workspace close/reopen. Groups are recreated with their original colors and names; pinned tabs remain pinned.

---

## Privacy and data

**Is my data sent to Duotang's servers?**
No. All workspace data, tab history, notes, clippings, and settings are stored locally in Chrome's storage APIs on your device. Nothing is uploaded to Duotang or any third-party service for storage purposes.

**Does Duotang collect any analytics or telemetry?**
No. There is no telemetry, no analytics, no tracking pixels, and no third-party scripts. Crash reports are opt-in; if you enable them, reports are fully anonymous with no way to link a report to a specific user or installation.

**Do I need an account?**
No. Duotang works without an account. There are no user IDs, install IDs, or device fingerprints of any kind.

**What network requests does Duotang make?**
Only on your behalf, for features you use: currency exchange rates (when you highlight a price), Wikipedia article summaries (when you hover a link or use Wikipedia highlights), map tiles (when Workbench Maps is open), and scripture lookups via Sefaria (when you highlight a verse reference). Each network-using feature is individually labelled and toggleable. A Paranoid mode in Settings blocks all outbound calls if you want guaranteed network silence.

---

## Features

**How is Duotang different from Toby, OneTab, or Tab Session Manager?**
Those tools save and restore URLs — when you switch contexts, your current tabs close and new ones open from saved URLs. Every switch reloads the page from scratch. Duotang keeps your tabs alive during every switch, so nothing reloads and no state is lost. See [duotang.co/guide/tab-managers](https://duotang.co/guide/tab-managers) for a detailed breakdown of the five categories of tab managers.

**How is Duotang different from Workona?**
Both keep tabs alive across workspace switches — that's the same architecture. The differences: Workona syncs all your tab URLs to their cloud servers and requires an account; Duotang is local-first with no account. Workona charges $7/month for full use; Duotang is free. Workona uses a pinned workona.com tab as its control surface; Duotang uses a collapsible sidebar injected on every page. Duotang also adds Highlights, Search+, Peek, Workbench, and workspace-scoped downloads that Workona does not include. See [duotang.co/vs/workona](https://duotang.co/vs/workona) for a full comparison.

**Does Find & Switch search my browsing history?**
Yes, with workspace context. Duotang's history records which workspace you were in when you visited each URL. Search results show workspace attribution, so you can see at a glance which project a page belongs to. History search is one of eight source types you can toggle individually in Settings.

**What does Peek do?**
Peek opens any link in a floating overlay alongside your current page — you never navigate away and your current page's state is untouched. Trigger it with Alt+click on any link, or right-click for the Peek pill. Peek works on sites that normally block iframing (Airbnb, Wirecutter, etc.). Includes a Reader mode for distraction-free article reading.

**What does Ctrl+Shift+Z do differently from Chrome's Ctrl+Shift+T?**
Chrome's built-in Ctrl+Shift+T restores the globally last-closed tab regardless of which workspace you're currently in. Duotang's Ctrl+Shift+Z restores the most recently closed tab in your current workspace — so if you closed a tab in your Work workspace, switching to Personal and pressing Ctrl+Shift+Z won't restore a Work tab by mistake.

---

## Compatibility and technical

**Does it work in Edge, Brave, or Vivaldi?**
Yes. Duotang is compatible with Chrome 121+ and other Chromium-based browsers including Edge, Brave, Vivaldi, and Opera. It is not compatible with Firefox.

**What happens if Chrome crashes?**
Duotang saves workspace state continuously. If Chrome crashes, your workspaces reopen with their tabs restored the next time you launch Chrome. The restore behavior is the same as a normal workspace close and reopen.

**Does Duotang work on `chrome://` pages or the Chrome Web Store?**
No. Chrome does not allow extensions to inject content scripts into `chrome://`, `chrome-extension://`, or Web Store pages. Duotang's sidebar, workspace bar, and Highlights features will not appear on those pages. This is a Chrome platform restriction, not a Duotang limitation.

**Does Duotang affect Chrome's Memory Saver?**
No. Duotang works alongside Chrome's built-in Memory Saver. Chrome can still suspend idle tabs within an open workspace; Duotang doesn't interfere with that. Duotang adds workspace-level memory management on top: closing an entire workspace's window frees all of that workspace's tabs from memory completely, which is a larger-scale operation than per-tab suspension.
