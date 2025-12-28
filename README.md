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
4. **Pair more Tabs**: Drag the **T** (T) icon to another existing tab to set as **Source** (S)

## 🎯 Key Features

- **Simple Controls**: Intuitive S (Source) and T (Target) indicators
- **Flexible Layouts**: Works with Chrome's Split View, separate windows, or multiple monitors
- **Media Controls**: Mute/unmute with `Ctrl+Alt+M`
- **Persistent**: Maintains state across page refreshes
- **Customizable**: Change mouse shortcuts via Tampermonkey menu

## 🖱️ How to Use

### Basic Usage
1. **Set Source Tab**
   - Go to your starting page
   - `CTRL` + **Middle-click** anywhere
   - Look for the **S** icon (top-right)

2. **Set Target Tab**
   - Go to where you want links to open
   - `ALT` + **Middle-click** anywhere
   - Look for the **T** icon (top-left)

3. **Start Browsing**
   - Click any link in Source → Opens in Target
   - Works with multiple Source tabs

### Advanced Controls
- **Pair Tabs**: Drag the **S** icon to a Target tab
- **Revoke**: Right-click S/T icon → Revoke
- **Disconnect**: Right-click S/T icon → Disconnect
- **Reset All**: Tampermonkey menu → Reset Roles

## ⚙️ Configuration

Customize in Tampermonkey → Configure Keys:
- **Source**: `CTRL` + `Middle Mouse` (default)
- **Target**: `ALT` + `Middle Mouse` (default)

## 📝 Version History

### v1.0.6 (Latest)
- Enhanced notification system with better responsive sizing
- Improved text wrapping in notifications for longer messages
- Persistent mute state across navigation
- Fixed media controls

[View all versions](https://github.com/neoxush/chrome-enhancedsplitview/commits/main)

---

💡 **Tip**: Works best when both tabs are visible (not minimized)

[Report Issues](https://github.com/neoxush/chrome-enhancedsplitview/issues) | [View on GitHub](https://github.com/neoxush/chrome-enhancedsplitview)
