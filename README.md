# Enhanced Split View for Chrome

Easily browse and view content side by side. Click links in one tab and see them open in another, perfect for research, coding, or comparing web pages. Works with Chrome's Split View, separate windows, or across multiple monitors.

## How it Works
![chrome_split_view_preview](https://github.com/user-attachments/assets/cb101a97-e580-412f-9844-1cb3befa3e3b)

## Installation
1. Install a userscript manager like [Tampermonkey](https://www.tampermonkey.net) or Violentmonkey.
2. Create a new script and copy/paste the code from `enhanced-split-view-for-chrome.user.js` in this repository.
3. Save the script.
*Click [here](https://github.com/neoxush/chrome-enhancedsplitview/raw/refs/heads/main/enhanced-split-view-for-chrome.user.js) to install userscript if you already had everything

## Changelog

### v1.0.6 (Latest)
- **Persistent Mute State**: Added tracking of mute state across page navigations
- **Media Controls**: Fixed mute state persistence when clicking links

<details>
<summary>View Older Versions</summary>

### v1.0.5
- **Enhanced Media Controls**: Improved media element tracking and state management
- **UI/UX Improvements**: Smoother animations and visual feedback for role changes
- **Performance**: Optimized event listeners and reduced memory usage
- **Bug Fixes**: Fixed edge cases in tab state synchronization
- **Accessibility**: Improved keyboard navigation and screen reader support
- **Mobile Support**: Better handling of touch events for mobile browsers
- **Security**: Added additional validation for cross-origin requests
- **Documentation**: Updated usage guide and configuration options

### v1.0.4
- Added media controls and mute functionality (Ctrl+Alt+M)
- Improved state persistence and UI feedback
- Enhanced drag & drop accuracy

### v1.0.3
- Implemented cross-tab bidding system
- Added focus-aware role assignment
- Enhanced debug logging

### v1.0.2
- Added Reset Roles menu
- Improved state persistence
- Enhanced drag-and-drop pairing
- Added configurable shortcuts

### v1.0.1
- Added context menu to S/T icons
- Introduced Revoke functionality

</details>

### Key Improvements Over Time

- **Media Handling**: Added comprehensive media controls with mute/unmute functionality and visual feedback
- **UI/UX**: Progressively enhanced interface with smoother animations and better visual feedback
- **Performance**: Optimized event handling and memory usage
- **Reliability**: Improved state management and persistence
- **Accessibility**: Better keyboard navigation and screen reader support
- **Mobile**: Enhanced touch event handling for mobile browsers

## Features

### Getting Started

<details>
<summary>📋 View Step-by-Step Guide</summary>

### 1. Create a Source Tab
1. Navigate to the page you want to use as your source
2. Hold `CTRL` + **Middle-click** anywhere on the page
3. Look for the floating **S** indicator in the top-right corner

### 2. Create a Target Tab
1. Open or switch to another tab where you want content to appear
2. Hold `ALT` + **Middle-click** anywhere on the page
3. Look for the floating **T** indicator in the top-left corner

### 3. Pair Source and Target
1. Hover over the **S** indicator in the source tab
2. Click and hold, then drag slightly to the right
3. Release to automatically pair with the target tab
4. The connection is now active - links in the source will open in the target

</details>

#### Quick Reference
- **Source Creation**: `CTRL` + **Middle-click** to mark as **SOURCE** (S)
- **Target Creation**: `ALT` + **Middle-click** to mark as **TARGET** (T)
- **Pairing**: Drag the "S" icon to pair with a target tab

### 2. Core Functionality
   1. **Link Syncing**  
      Any link clicked in the Source tab automatically opens in the Target tab.
   
   2. **Visual Interface**  
      - Floating "S" (Source) and "T" (Target) indicators
      - Context menus for control
      - Visual feedback for actions

### 3. Advanced Features
   1. **Media Controls**  
      - Mute/unmute with `Ctrl+Alt+M`
      - Visual feedback for muted state
      - Automatic media handling
   
   2. **Customization**  
      - Configurable mouse shortcuts
      - Visual configuration panel
      - Adjustable UI positioning

### 4. Layout & Management
   1. **Layout Options**  
      - Chrome's native Split View
      - Separate windows
      - Dual monitor support
   
   2. **Group Management**  
      - Multiple Source tabs per group
      - Dynamic Target assignment
      - Context menu controls

### 5. Reliability
   - **State Persistence** across page refreshes
   - **Automatic Recovery** of connections
   - **Error Handling** with visual feedback

## Usage Guide
### 1. Set Up Your View
Open the two pages you want to use.
*   **Split View**: Use Chrome's native tiling if supported.
*   **Separate Windows**: Simply put two browser windows side-by-side.
    <br><img width="283" height="142" alt="image" src="https://github.com/user-attachments/assets/13fc0fae-485d-4934-aead-7fced7c3bbed" /></br>

### 2. Activate Source
In your main window, hold `CTRL` + **Middle Mouse Button** (default). A floating **S** icon will appear on the right side.
*   *Note: You can configure this shortcut by selecting "Configure Keys" from the Tampermonkey menu.*

### 3. Activate Target
Ensure your desired Target tab/window is visible (not minimized).
*   **Drag Method**: Click and hold the **S** icon on the Source page, drag it slightly, and release. The other visible tab will detect the signal and become the **TARGET** (marked with a **T** icon on the left side).
*   **Manual Method**: Hold `ALT` + **Middle Mouse Button** (default) in any tab to make it a Target connected to the most recent Source.
*   **Join Existing Group**: Use the "Join as Source" option from the S/T context menu to add additional Source tabs to an existing group.

### 4. Browse
Click any link in the **Source** tab. It will automatically load in the **Target** tab.

### 5. Manage Connections
- **Revoke**: Right-click the S/T indicator and select "Revoke" to disconnect just this tab.
- **Disconnect**: Right-click the S/T indicator and select "Disconnect" to break the connection between both tabs.
- **Reset All**: Use "Reset Roles" from the Tampermonkey menu to clear all connections across all tabs.

## Configuration
You can customize the mouse shortcuts by selecting **Configure Keys** from the Tampermonkey menu:
- **Source Key**: Default is `CTRL` + `Middle Mouse Button`
- **Target Key**: Default is `ALT` + `Middle Mouse Button`
- Both support Left (0), Middle (1), and Right (2) mouse buttons with Ctrl/Alt/Shift modifiers.

## Tampermonkey Menu Commands
- **Create Source**: Manually set current tab as a Source
- **Configure Keys**: Open the visual configuration panel
- **Reset Roles**: Clear all Source/Target connections across all tabs
