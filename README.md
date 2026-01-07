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

### v1.0.8 (Latest)
- **New Playlist Feature**: Double-click target tab to enter playlist mode for managing multiple links
- **Playlist Sharing**: Share your playlist with others or export/import playlists for later use
- **Enhanced Media Controls**: Improved lazyload mute system with persistent state across sessions
- **Better UI**: Added mini playlist controls with previous/next navigation
- **Improved Notifications**: Modern notification system with better responsive design and text wrapping
- **Enhanced State Management**: More robust tab state persistence across navigation
- **Fullscreen Support**: UI automatically hides/shows based on fullscreen state
- **SPA Improvements**: Better support for single-page applications like YouTube

[View all versions](https://github.com/neoxush/chrome-enhancedsplitview/commits/main)

## 🎯 Key Features

- **Simple Controls**: Intuitive S (Source) and T (Target) indicators
- **Playlist Mode**: Double-click target tabs to manage multiple links with playlist controls
- **Playlist Sharing**: Export and share playlists with others or import playlists for later use
- **Flexible Layouts**: Works with Chrome's Split View, separate windows, or multiple monitors
- **Media Controls**: Mute/unmute with `Ctrl+Alt+M` and persistent mute state
- **Smart UI**: Auto-hides in fullscreen, responsive design with modern notifications
- **Persistent**: Maintains state across page refreshes and navigation
- **Customizable**: Change mouse shortcuts via Tampermonkey menu
- **SPA Support**: Enhanced compatibility with single-page applications

## ⚙️ Configuration

Customize in Tampermonkey → Configure Keys:
- **Source**: `CTRL` + `Middle Mouse` (default)
- **Target**: `ALT` + `Middle Mouse` (default)

---

💡 **Tip**: Works best when both tabs are visible (not minimized)

[Report Issues](https://github.com/neoxush/chrome-enhancedsplitview/issues) | [View on GitHub](https://github.com/neoxush/chrome-enhancedsplitview)
