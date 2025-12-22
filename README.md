# Enhanced Split View for Chrome

This userscript syncs navigation between two Chrome tabs: a **Source** and a **Target**. 

While originally designed to supercharge Chrome's native Side-by-Side "Split View", it functions perfectly with **any two individual Chrome tabs or windows** (e.g., dual monitors, separate windows side-by-side), allowing you to click links in one and view them in the other.

## Changelog

### v1.0.5 (Latest)
- **Enhanced Media Controls**: Improved media element tracking and state management
- **UI/UX Improvements**: Smoother animations and visual feedback for role changes
- **Performance**: Optimized event listeners and reduced memory usage
- **Bug Fixes**: Fixed edge cases in tab state synchronization
- **Accessibility**: Improved keyboard navigation and screen reader support
- **Mobile Support**: Better handling of touch events for mobile browsers
- **Security**: Added additional validation for cross-origin requests
- **Documentation**: Updated usage guide and configuration options

<details>
<summary>View Older Versions</summary>

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
1. **Source Creation**: Hold `CTRL` + **Middle-click** (default) anywhere on a page to mark it as the **SOURCE** (S).
2. **Target Creation**: Hold `ALT` + **Middle-click** (default) to mark current tab as **TARGET** (T) and connect to the most recent Source.
3. **Easy Pairing (Drag & Drop)**: Once you have a Source, click and hold the "S" icon, drag it, and release. The script will automatically pair with the other currently visible tab (the **TARGET**).
4. **Link Syncing**: Any link clicked in the Source tab automatically opens in the Target tab.
5. **Visual Interface**: Floating "S" (Source) and "T" (Target) indicators with context menus for control.
6. **Media Controls**: Mute/unmute media in source tabs with Ctrl+Alt+M or via the UI.
7. **Hotkey Customization**: Fully configurable mouse shortcuts via the visual configuration panel.
8. **Flexible Layouts**: Works with Chrome's native Split View, two separate windows, or dual monitors.
9. **Group Management**: Multiple Source tabs can be grouped together, with Targets joining existing groups.
10. **State Persistence**: Tab roles and connections survive page refreshes and navigation changes.
11. **Context Menu Controls**: Right-click on S/T indicators for options like Revoke, Disconnect, and Join as Source.

## How it Works
![chrome_split_view_preview](https://github.com/user-attachments/assets/cb101a97-e580-412f-9844-1cb3befa3e3b)

## Installation
1. Install a userscript manager like [Tampermonkey](https://www.tampermonkey.net) or Violentmonkey.
2. Create a new script and copy/paste the code from `enhanced-split-view-for-chrome.user.js` in this repository.
3. Save the script.
*Click [here](https://github.com/neoxush/chrome-enhancedsplitview/raw/refs/heads/main/enhanced-split-view-for-chrome.user.js) to install userscript if you already had everything

## Usage Guide

<div class="tab-container">
  <div class="tabs">
    <button class="tab-button active" onclick="openTab(event, 'setup')">1. Setup</button>
    <button class="tab-button" onclick="openTab(event, 'source')">2. Activate Source</button>
    <button class="tab-button" onclick="openTab(event, 'target')">3. Activate Target</button>
    <button class="tab-button" onclick="openTab(event, 'browse')">4. Browse</button>
    <button class="tab-button" onclick="openTab(event, 'manage')">5. Manage</button>
  </div>

  <div id="setup" class="tab-content" style="display: block;">
    <h3>Set Up Your View</h3>
    <p>Open the two pages you want to use.</p>
    <ul>
      <li><strong>Split View</strong>: Use Chrome's native tiling if supported.</li>
      <li><strong>Separate Windows</strong>: Simply put two browser windows side-by-side.</li>
    </ul>
    <img width="283" height="142" alt="Split View Example" src="https://github.com/user-attachments/assets/13fc0fae-485d-4934-aead-7fced7c3bbed" />
  </div>

  <div id="source" class="tab-content">
    <h3>Activate Source</h3>
    <p>In your main window, hold <code>CTRL</code> + <strong>Middle Mouse Button</strong> (default). A floating <strong>S</strong> icon will appear on the right side.</p>
    <div class="note">
      <strong>Note:</strong> You can configure this shortcut by selecting "Configure Keys" from the Tampermonkey menu.
    </div>
  </div>

  <div id="target" class="tab-content">
    <h3>Activate Target</h3>
    <p>Ensure your desired Target tab/window is visible (not minimized).</p>
    
    <h4>Drag Method</h4>
    <p>Click and hold the <strong>S</strong> icon on the Source page, drag it slightly, and release. The other visible tab will detect the signal and become the <strong>TARGET</strong> (marked with a <strong>T</strong> icon on the left side).</p>
    
    <h4>Manual Method</h4>
    <p>Hold <code>ALT</code> + <strong>Middle Mouse Button</strong> (default) in any tab to make it a Target connected to the most recent Source.</p>
    
    <h4>Join Existing Group</h4>
    <p>Use the "Join as Source" option from the S/T context menu to add additional Source tabs to an existing group.</p>
  </div>

  <div id="browse" class="tab-content">
    <h3>Browse with Split View</h3>
    <p>Once you have a Source and Target connected, simply click any link in the <strong>Source</strong> tab. The link will automatically load in the <strong>Target</strong> tab.</p>
  </div>

  <div id="manage" class="tab-content">
    <h3>Manage Connections</h3>
    <div class="action-item">
      <h4>Revoke</h4>
      <p>Right-click the S/T indicator and select "Revoke" to disconnect just this tab.</p>
    </div>
    
    <div class="action-item">
      <h4>Disconnect</h4>
      <p>Right-click the S/T indicator and select "Disconnect" to break the connection between both tabs.</p>
    </div>
    
    <div class="action-item">
      <h4>Reset All</h4>
      <p>Use "Reset Roles" from the Tampermonkey menu to clear all connections across all tabs.</p>
    </div>
  </div>
</div>

<style>
.tab-container {
  margin: 20px 0;
  border: 1px solid #e1e4e8;
  border-radius: 6px;
  overflow: hidden;
}
.tabs {
  display: flex;
  background-color: #f6f8fa;
  border-bottom: 1px solid #e1e4e8;
  padding: 0 10px;
  flex-wrap: wrap;
}
.tab-button {
  background: none;
  border: none;
  padding: 10px 16px;
  cursor: pointer;
  font-size: 14px;
  color: #24292e;
  border-bottom: 2px solid transparent;
  margin: 0 4px -1px 0;
  white-space: nowrap;
}
.tab-button:hover {
  color: #0366d6;
}
.tab-button.active {
  background-color: #fff;
  border-color: #e36209;
  color: #24292e;
  font-weight: 500;
}
.tab-content {
  display: none;
  padding: 20px;
  background-color: #fff;
}
.tab-content h3 {
  margin-top: 0;
}
.note {
  background-color: #f6f8fa;
  border-left: 4px solid #0366d6;
  padding: 10px 15px;
  margin: 10px 0;
  border-radius: 0 3px 3px 0;
}
.action-item {
  margin-bottom: 15px;
}
.action-item:last-child {
  margin-bottom: 0;
}
</style>

<script>
function openTab(evt, tabName) {
  const tabContents = document.getElementsByClassName("tab-content");
  for (let i = 0; i < tabContents.length; i++) {
    tabContents[i].style.display = "none";
  }
  const tabButtons = document.getElementsByClassName("tab-button");
  for (let i = 0; i < tabButtons.length; i++) {
    tabButtons[i].className = tabButtons[i].className.replace(" active", "");
  }
  document.getElementById(tabName).style.display = "block";
  evt.currentTarget.className += " active";
}
</script>

## Configuration
You can customize the mouse shortcuts by selecting **Configure Keys** from the Tampermonkey menu:
- **Source Key**: Default is `CTRL` + `Middle Mouse Button`
- **Target Key**: Default is `ALT` + `Middle Mouse Button`
- Both support Left (0), Middle (1), and Right (2) mouse buttons with Ctrl/Alt/Shift modifiers.

## Tampermonkey Menu Commands
- **Create Source**: Manually set current tab as a Source
- **Configure Keys**: Open the visual configuration panel
- **Reset Roles**: Clear all Source/Target connections across all tabs
