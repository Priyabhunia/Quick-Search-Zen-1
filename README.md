# ⭐ Quick Search - Zen Browser ⭐
Script to quickly search for a word or phrase in the Zen Browser through a pop up thus removing the need to create and swtich to a new tab.

## Search Popup[I fixed this for myself only There is no chance that I can maintain this, so if you want to edit just fork it and do it yourself]

https://github.com/user-attachments/assets/95702ac2-96bf-478e-8e47-0afa4916c1c2


## Glance Mode




https://github.com/user-attachments/assets/827215fc-e985-4f71-8646-6e3a6b7e624b





## ✨ Features

### 🔍 **Search Capabilities**
- Uses search engines defined within the browser
- Support for search engine prefixes (@google, @ddg, @bing, etc.)
- Context menu integration for selected text searches
- Global keyboard shortcut for instant access
- Dynamic search engine selector for quickly changing search engine

### 🎨 **Customizable Interface**
- **Multiple themes**: Dark, light, and auto (system-based)
- **Flexible positioning**: Top-right, top-left, center, bottom corners
- **Resizable container**: Drag to resize, remembers your preferred size
- **Smooth animations**: Configurable slide-in/out effects
- **Drag and Drop**: Resize and change position easily with drag and drop 

### ⚡ **Advanced Functionality**
- **Zen Glance Mode**: Launch searches in Zen Browser's Glance mode
- **Auto-focus**: Automatically focus search input for faster typing
- **Content scaling**: Adjustable zoom for better readability
- **Persistent settings**: All preferences saved between browser sessions

### 🛠️ **Configuration Options**
- **13+ customizable preferences** through Firefox's about:config
- **JSON-based configuration** for easy setup and sharing
- **Real-time preference changes** (most settings apply immediately)
- **Backward compatibility** with existing installations



## 🔧 Installation

### Method 1: Through [Sine](https://github.com/CosmoCreeper/Sine) — recommended

Sine is the mod manager for Zen. If you don't have it yet, install it first by
following [Sine's install instructions](https://github.com/CosmoCreeper/Sine),
then restart Zen.

1. **Allow JS mods** — Open Zen Settings (`about:preferences`) and click
   **Sine Mods** in the left sidebar, then open Sine's **Settings** (gear icon).
   Turn on **"Enable installing JS from unofficial sources"**.

   > This mod ships a `.uc.js` script. Without this toggle Sine accepts the
   > install but silently never loads the script, and nothing happens when you
   > press the shortcut.

2. **Install the mod** — In the same **Sine Mods** pane, find the **Install**
   box, type this repo and click **Install**:

   ```
   Priyabhunia/Quick-Search-Zen-1
   ```

3. **Restart Zen.** Mods are loaded when a browser window is created, so the
   shortcut will not work until you restart.

4. **Use it** — press `Ctrl + Space` anywhere in the browser.

If `Ctrl + Space` does nothing, something else on your system has claimed it
(a common case is an IME input-mode toggle). Change it to any other combination
in Sine's mod settings or in `about:config`, then restart Zen:

```
extensions.quicksearch.shortcuts.toggle_key
```

### Method 2: Manual install (advanced)

1. **Download the Files**
   - Go to the [fx-autoconfig GitHub page](https://github.com/MrOtherGuy/fx-autoconfig/tree/master).
   - Click the green `< > Code` button and download the ZIP file.

2. **Navigate to Your Zen Browser Installation Folder**
   - Locate your Zen Browser installation folder:
     - Default location on Windows: `C:\Program Files\Zen Browser`.
     - If unsure, open `about:support` in Zen Browser, and look for the "Application Binary" field.

3. **Extract fx-autoconfig ZIP File**
   - Open the extracted folder and locate the `program` folder. Inside, you’ll find:
     - A `defaults` folder.
     - A `config.js` file.

4. **Move Files to the Installation Folder**
   - You can **merge** or **replace** the files depending on your preferred method:
     - **Merge**:
       - **config.js**: Open the `config.js` file from the ZIP. 
         - If a `config.js` file exists in your Zen Browser folder, copy its content from the ZIP version and paste it into your existing file, then save.
         - If no `config.js` file exists, copy the one from the ZIP directly to your Zen Browser folder.
       - **defaults folder**: Navigate to `defaults > pref > config-prefs.js` both in the ZIP and Zen Browser folder. Open both files, copy the content from the ZIP version, and paste it into the existing file in Zen Browser. If the folder or file doesn’t exist, simply copy the entire `defaults` folder into your Zen Browser folder.
     - **Replace**:
       - Drag and drop the entire `defaults` folder and `config.js` from the ZIP file into the Zen Browser installation folder. Replace any existing files when prompted.

5. **Navigate to Your Zen Profile Folder**
   - Open Zen Browser and go to `about:profiles`.
   - Locate the desired profile, find the "Root Directory," and click "Open Folder."

6. **Copy the Profile Files**
   - Go back to the `profile` folder in the fx-autoconfig ZIP.
   - Copy the `chrome` folder into the profile's root directory.


#### Then: install Quick Search itself

1. **Open the Required Folder**
   - From your profile root folder, navigate to `chrome > JS`.

2. **Download the Quick Search Plugin**
   - Go to the [Quick Search GitHub page](https://github.com/Priyabhunia/Quick-Search-Zen-1/tree/main).
   - Click the green `< > Code` button and download the ZIP file.

3. **Check Configuration in Zen Browser**
   - Open a new tab, type `about:config`, and press Enter.
   - Look up `zen.urlbar.replace-newtab`. Note whether it is set to `true` or `false`.

4. **Install the Plugin**
   - Extract the Quick Search ZIP file.
   - Depending on the `zen.urlbar.replace-newtab` value:
     - If `false`: Copy `quickSearch_NoBar.uc.js` from the extracted ZIP to the `JS` folder.
     - If `true`: Copy `quickSearch.uc.js` from the extracted ZIP to the `JS` folder.
   - **Optional**: Copy `preferences.json` to your profile folder if you plan to use a preferences management UI.

5. **Clear Startup Cache**
   - Open `about:support` in Zen Browser.
   - Click "Clear startup cache..." in the top-right corner. When prompted, restart the browser.

6. **Configure Preferences (Optional)**
   - After installation, you can customize Quick Search through `about:config`
   - Search for `extensions.quicksearch` to see all available options
   - See the [Configuration](#️-configuration) section for detailed preference descriptions



## ⚙️ Configuration

Quick Search now supports comprehensive customization through Firefox's preference system. You can configure all settings through `about:config` or using a preferences UI that supports the included `preferences.json` file.

### 🎛️ Available Preferences

All preferences are located under the `extensions.quicksearch.*` branch in `about:config`:

#### **Context Menu Settings**
- `extensions.quicksearch.context_menu.enabled` (boolean, default: true)
  - Enable/disable the right-click context menu integration
- `extensions.quicksearch.context_menu.engine` (string, default: "@ddg")
  - Default search engine for context menu searches (e.g., "@google", "@bing", "@ddg")
- `extensions.quicksearch.context_menu.access_key` (string, default: "Q")
  - Keyboard shortcut letter for the context menu item

#### **Container Appearance**
- `extensions.quicksearch.container.width` (integer, default: 550)
  - Default width of the Quick Search popup container (200-1200px)
- `extensions.quicksearch.container.height` (integer, default: 300)
  - Default height of the Quick Search popup container (150-800px)
- `extensions.quicksearch.container.position` (string, default: "top-right")
  - Container position: "top-right", "top-left", "center", "bottom-right", "bottom-left"
- `extensions.quicksearch.container.theme` (string, default: "dark")
  - Visual theme: "dark", "light", "auto" (follows system theme)

#### **Behavior Settings**
- `extensions.quicksearch.behavior.animation_enabled` (boolean, default: true)
  - Enable/disable slide-in/slide-out animations
- `extensions.quicksearch.behavior.remember_size` (boolean, default: true)
  - Remember and restore container dimensions between sessions
- `extensions.quicksearch.behavior.drag_resize_enabled` (boolean, default: true)
  - Enable Resize and drag and drop.
- `extensions.quicksearch.behavior.auto_focus` (boolean, default: true)
  - Automatically focus search input when Quick Search opens

#### **Keyboard Shortcuts**
- `extensions.quicksearch.shortcuts.toggle_key` (string, default: "Ctrl+Space")
  - Global keyboard shortcut to toggle Quick Search (supports Ctrl+Shift+Alt combinations, and named keys such as `Space`, `Enter`, `Escape`)
- `extensions.quicksearch.shortcuts.escape_closes` (boolean, default: true)
  - Allow Escape key to close the Quick Search container

### 🛠️ How to Configure

#### **Method 1: Using about:config**
1. Open a new tab and navigate to `about:config`
2. Accept the warning if prompted
3. Search for `extensions.quicksearch`
4. Modify any preference by double-clicking on it
5. Restart Zen Browser for changes to take effect

#### **Method 2: Using Preferences UI**
If you have a preferences management tool that supports JSON configuration:
1. Use the included `preferences.json` file
2. Import it into your preferences manager
3. Configure settings through the UI

#### **Method 3: Manual Configuration**
You can also manually edit preferences by creating a `user.js` file in your profile folder with your desired settings:

```javascript
// Example user.js configuration
user_pref("extensions.quicksearch.container.theme", "light");
user_pref("extensions.quicksearch.container.position", "center");
user_pref("extensions.quicksearch.shortcuts.toggle_key", "Ctrl+Alt+S");
user_pref("extensions.quicksearch.behavior.animation_enabled", false);
```

### 🎨 Theme Examples

**Dark Theme (default):**
- Container: Dark background with light text
- Suitable for dark browser themes

**Light Theme:**
- Container: Light background with dark text
- Suitable for light browser themes

**Auto Theme:**
- Automatically switches between dark and light based on system preferences

## 🔍 Usage

Quick Search supports multiple ways to perform searches and uses your browser's default search engines (e.g., '@google', '@ddg', '@bing').

### 📝 Search Methods

#### **URL Bar Method** (quickSearch.uc.js):
1. Open the URL bar and type your search query
2. Press `Ctrl + Enter` to open the search popup
3. Press `Ctrl + Shift + Enter` to open in Zen Glance Mode

#### **Direct Search Method** (quickSearch_NoBar.uc.js):
1. Press `Ctrl + Enter` to open the search popup
2. Type your search query in the input field
3. Press `Enter` to search

#### **Global Keyboard Shortcut** (New Feature):
1. Press `Ctrl + Space` (or your configured shortcut) anywhere in the browser
2. Type your search query in the popup input
3. Press `Enter` to search
4. Press the same shortcut again to close the popup

#### **Right-Click Context Menu**:
1. Select any text on a webpage
2. Right-click and choose "Open in Quick Search" (or press `Q`)
3. The selected text will be searched automatically

### 🎯 Search Engine Prefixes

Use these prefixes to search with specific engines:
- `@google your query` - Search with Google
- `@ddg your query` - Search with DuckDuckGo  
- `@bing your query` - Search with Bing
- `@youtube your query` - Search YouTube
- And any other search engines you have configured in your browser

### ⌨️ Keyboard Shortcuts Summary

| Shortcut | Action |
|----------|--------|
| `Ctrl + Enter` (in URL bar) | Open Quick Search popup |
| `Ctrl + Shift + Enter` (in URL bar) | Open in Zen Glance Mode |
| `Ctrl + Space` | Global toggle Quick Search popup |
| `Escape` | Close Quick Search popup |
| `Enter` (in search input) | Execute search |
| `Q` (in context menu) | Access Quick Search from right-click menu |

### 🎨 Visual Features

- **Themes**: Dark, light, or auto themes that adapt to your system
- **Positioning**: Place the popup anywhere on screen (corners, center)
- **Animations**: Smooth slide-in/out effects (can be disabled)
- **Resizable**: Drag the corner to resize the popup
- **Responsive**: Automatically scales content to fit the container

