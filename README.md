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

### v1.3.3 (Latest)
- **Color system — decouple role hues from status hues**: Source `#22c55e` → `#10b981` (emerald), Target `#3b82f6` → `#6366f1` (indigo), Playlist `#a855f7` → `#f43f5e` (rose). Info `#3b82f6` → `#0ea5e9` (sky). Save button, focus rings, and checkboxes no longer visually read as "Target"; Success toast no longer shares a hex with the Source dot.
- **Accessibility**: `.stm-playlist-item.playing` now carries a `▶` glyph via `::before` so state is readable without color perception (WCAG SC 1.4.1).
- **Design tokens**: Every role/status hue now exposes a matching `*-rgb` triplet token so translucent tints (glow shadows, `.active`/`.playing` backgrounds) reference the token instead of hardcoded `rgba()`. Palette is a single source of truth — future palette changes are a 6-line edit.

### v1.3.2
- **Perf — role-churn & data transmission**: `saveState()` no longer rewires GM value-change listeners when role/id are unchanged (kills wasted churn on mute toggles and target-received navigations). `KEY_UI_POS` write skipped when position is unchanged. Playlist render-skip hash changed from `O(N)` `JSON.stringify(playlist.map(i=>i.url))` to an `O(1)` version counter — matters on 100+ item playlists.

### v1.3.1
- **Bugfix — playlist panel leak**: Playlist panel could persist into non-playlist roles after cycling `playlist → revoke → target`. Now defensively hidden in `updateUI()` for any non-playlist role, with the same guard added to `toggleMenu()`.

### v1.3.0
- **Compact floating UI**: Dot 32→26, volume 28→24, mini prev/next 26→22, menu 160→124 with tighter row padding (10→5), playlist panel 280→240 with tighter rows and empty state.
- **Accessibility**: Keyboard + ARIA on status dot (Enter/Space toggles menu), volume button (`aria-pressed` reflects mute), mini-playlist buttons, playlist rows (Enter/Space to open, Delete/Backspace to remove), source picker items. Config panel is now a proper `role="dialog"` with `aria-modal`, `aria-labelledby`, focus trap, and focus restore on close.
- **Perf — general**: `MutationObserver` uses `querySelectorAll` instead of serializing `outerHTML` (major win on React/Vue SPAs). Grip drag caches heights at `mousedown` — no layout thrash per mousemove. Notification `_restack` batched via `requestAnimationFrame`. `mediaManager` tick self-schedules (no overlap). Global capture listeners marked `{ passive: true }` where safe. Config-panel field refs cached once (killed 15+ `getElementById` per open/save).
- **Reduced motion**: `@media (prefers-reduced-motion: reduce)` now applies globally via `*` selectors.
- **Design tokens**: `backdrop-filter` consolidated into 4 CSS custom properties.

### v1.2.1
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
