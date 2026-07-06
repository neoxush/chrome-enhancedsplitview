# Enhanced Split View for Chrome

Browse and view content side by side with ease. Click links in one tab and see them open in another - perfect for research, coding, or comparing web pages.

![Demo](https://github.com/user-attachments/assets/cb101a97-e580-412f-9844-1cb3befa3e3b)

## 🚀 Quick Start

1. **Install** the userscript using [Tampermonkey](https://www.tampermonkey.net) or [install directly](https://github.com/neoxush/chrome-enhancedsplitview/raw/refs/heads/main/enhanced-split-view-for-chrome.user.js)
2. **Setup**
   - Open two browser windows/tabs
   - In first window: `CTRL` + **Middle-click** to set as **Source** (S)
   - In second window: `ALT` + **Middle-click** to set as **Target** (T)
     OR Drag the **S** icon to an existing tab to set as **Target** (T)
3. **Use**: Click links in Source to open them in Target
4. **Playlist Mode**: Double-click the **T** icon to enter playlist mode, then use mini controls to navigate between links
5. **Pair more Tabs**: Drag the **T** (T) icon to another existing tab to set as **Source** (S)

## 📝 Version History

### v1.2.1 (Latest)
- **Bugfix — Trusted Types compliance**: `updateVolumeButton` sleep-mode icon now routes through the script's Trusted Types policy (`ttPolicy.createHTML`), matching every other `innerHTML` write in the script. Without this, sites that enforce Trusted Types via CSP (e.g. `play.google.com`) blocked the icon assignment, causing the volume/mute-control button to silently fail to render and producing inconsistent pair-drag / source-transmission behavior on those pages.

### v1.2.0
- **AI Chat Site Compatibility**: Drag-to-pair now works reliably on ChatGPT, Gemini, Claude, Perplexity, and similar AI chat apps. Pages with global file-upload overlays no longer freeze on pair drop — fixed via strict event isolation (`dragenter`/`dragover`/`drop` stop propagation on our role-request payload).
- **Performance**: Removed always-on global `mousemove` listener (now lazy-attached only during in-flight drags). YouTube Shorts polling now stops once the player is detected (saves perpetual 2s ticks).
- **Code Health**: Centralized role-drag MIME detection and event isolation into helper functions — single source of truth, easier to extend.
- **New Debug Toggle**: Tampermonkey menu entry "ESV debug logs: ON/OFF (toggle)" lets you enable verbose `[ESV]` logging without editing the script.

### v1.1.0
- **Low-Latency Sync**: Faster communication between tabs using `BroadcastChannel`.
- **Keyboard Shortcuts**: New power-user shortcuts for muting, playlist navigation, and UI control.
- **Premium Design System**: Overhauled UI with modern design tokens, glassmorphism, and smooth animations.
- **Notification Queueing**: Notifications now queue and stack (max 3), with pause-on-hover functionality.
- **Multi-Source Support**: Better management for multiple source tab environments.
- **Enhanced Configuration**: Customize themes and keyboard shortcut preferences.

### v1.0.8
- **New Playlist Feature**: Double-click target tab to enter playlist mode for managing multiple links
- **Playlist Sharing**: Share your playlist with others or export/import playlists for later use

[View all versions](https://github.com/neoxush/chrome-enhancedsplitview/commits/main)

## 🎯 Key Features

- **Simple Controls**: Intuitive S (Source) and T (Target) indicators with premium glassmorphism.
- **Low-Latency Sync**: Real-time cross-tab signaling using `BroadcastChannel`.
- **Keyboard Power User Shortcuts**: Quick access to mute, navigation, and UI dismissal.
- **Playlist Mode**: Double-click target tabs to manage multiple links with playlist controls.
- **Media Controls**: Mute/unmute with `M` key and persistent mute state across sessions.
- **Smart UI**: Auto-hides in fullscreen, responsive design with queued modern notifications.
- **Persistent**: Maintains state across page refreshes and navigation.
- **Customizable**: Change mouse shortcuts, themes, and keyboard bindings via the Preference panel.

## ⌨️ Keyboard Shortcuts

- `M`: Toggle Mute
- `Esc`: Close UI / Panels
- `Arrow Right / Left`: Next / Previous in Playlist
- `Alt + Shift + R`: Revoke current role

## ⚙️ Configuration

Customize in the new **Preference** panel (click the status dot) or via Tampermonkey:
- **Source/Target Keys**: Configure mouse button and modifiers.
- **Theme**: Auto / Light / Dark support.
- **Shortcuts**: Enable or disable specific keyboard bindings.

---

💡 **Tip**: Works best when both tabs are visible (not minimized)

[Report Issues](https://github.com/neoxush/chrome-enhancedsplitview/issues) | [View on GitHub](https://github.com/neoxush/chrome-enhancedsplitview)
