## 🛠️ Setup & Installation

- Download and install the latest version of the Setup.exe from Releases.

https://github.com/user-attachments/assets/ef47be36-fc9a-4424-a3e3-c695e523b2cd

## ➕ Creating User Profiles

![create_user](https://github.com/user-attachments/assets/2702ca46-a1ad-4e8d-a23f-24e8941edff4)

**Prerequisites:**

Chrome Profiles and Microsoft SSO extension paths are required for this app to work. This will work with your default work profile, but if you want to create a new profile or don't have a profile, the instructions can be found here: https://support.google.com/chrome/answer/2364824?hl=en&co=GENIE.Platform%3DDesktop

**Finding Your Profile Path:**

Once you have a profile you would like to use, you will need to know the path to both the profile and the Microsoft SSO extension in order to add a User.

**Profile Path:**

- `C:\Users\{Your UserName}\AppData\Local\Google\Chrome\User Data\Default` or `{Profile #}`

**Microsoft SSO Extension Path:**

- `C:\Users\{Your UserName}\AppData\Local\Google\Chrome\User Data\{Profile #}\Extensions\ppnbnpeolgkicgegkbkbjmhlideopiji`
- You no longer need to select the version number, this will iterate as updates are made.

**Creating a User:**

With a profile and the locations of the two folders, you will be ready to create a User by pressing the "Add User" button and completing the form.

**Note:** Profile data is stored locally on your machine at:

- `C:\Users\{Your UserName}\AppData\Roaming\estools\config.json`

## 🔍 Search Accounts

![search](https://github.com/user-attachments/assets/7b235297-40cb-45f5-ad30-f57d87130a33)

**How to Search for Accounts:**

1. Click on a User
2. Wait for the accounts to load - you will see a Chromium window pop up which will be automating the login process
3. After tenants load, select a tenant
4. After the search bar appears on the right, enter either:
   - A full BU #, or
   - A full or partial account name
5. Press Enter or click the Search button

**Shortcuts:**
From the account search, you have several options.
- Copy: copies data to the clipboard
   - Desktop Studio - provides the session ID for logging into desktop studio
   - URL - provides the API base URL
   - Token - provides an API token
- Launch: opens a new browser window session
   - Userhub: opens to "Impersonate and Support"
   - Web Studio: automatically navigates to web studio
   - Settings: selects the business unit after search but does not impersonate
   - Configure: opens to "Impersonate and Configure"
- Management (Admin and above): opens the BU's Studio scripts or files - see [Script & File Management](#-script--file-management)

**Refreshing or Switching Tenants:**

- To refresh or switch tenants, click the back button or your User profile. You will be presented again with the tenant list to select from.

## ⭐ Favorites

![favorites](https://github.com/user-attachments/assets/2c8bf80a-bab6-47e6-a4d3-7b2202b35bbc)

**How to Use Favorites:**

1. Load a Profile
2. Select a Tenant
3. Favorite BUs will display under the selected Tenant

**Adding a BU to Favorites:**

- Search for the BU
- Once the search results are loaded, click the star (☆) next to the BU you want to favorite

**Removing a BU from Favorites:**

- Click the star (★) next to the BU in the search results, or
- Right-click on the BU in the favorites section and select "Delete Favorite"

**Using Favorites:**

- Click on a specific BU in the favorites section to automatically perform a search for that BU

**Note:** Favorites are stored in the same config file as profile data (`C:\Users\{Your UserName}\AppData\Roaming\estools\config.json`).

## 📜 Script & File Management

A file manager for a single BU. It handles two file types:

- **Scripts**: Studio scripts
- **Files**: the BU's file server (prompts, audio, calling lists, and other uploaded files)

**Note:** The Management column is available to Admin roles and above.

**Opening Script & File Management:**

1. Search for the BU
2. In the Management column of the results:
   - Click **Scripts** to open Studio scripts, or
   - Click the **▾** arrow beside it and choose **Files**
3. To switch between Scripts and Files without leaving, use the file-type picker at the top of the page. Switching clears your current selection.
4. Click **Back** to return to the BU search

**The File Browser:**

- Click a folder to expand it, or use **Expand all** to load every folder
- Type in the filter box at the top to narrow the list by file or folder name
- Tick the checkbox next to a file to select it. Ticking a folder selects everything inside it.
- **Select all**, **Clear selection** and **↻ Refresh** are in the browser header
- Keyboard: **↑ / ↓** to move, **Space** to tick or untick, **Enter** to expand or collapse a folder, **Esc** to close an open panel

Once something is selected, an action bar appears at the bottom of the page:

| Action           | Scripts | Files | What it does                                                    |
| ---------------- | :-----: | :---: | --------------------------------------------------------------- |
| Promote…         |    ✅    |   ✅   | Copies the selection to a new path in the same BU (e.g. DEV → PROD) |
| Rename…          |         |   ✅   | Moves or renames the selection in place                         |
| Export           |    ✅    |   ✅   | Saves the selection to a folder on your computer                |
| Duplicate        |    ✅    |   ✅   | Makes a copy alongside the original                             |
| Delete           |    ✅    |   ✅   | Permanently deletes the selection                               |
| Variable redaction |  ✅    |       | Sets the redacted variables on the selected scripts             |

Progress for each action shows at the bottom of the page, and the result of each file is written to the log.

**TO PROMOTE:**

1. Select the scripts/files or folders you want to promote and click **Promote…**
2. Choose a scope:
   - **Whole folder**: copies the folder and keeps its structure at the target. In the Folder Path Mapping panel, edit the target folder name (e.g. change `DEV` to `PROD`). Subfolders follow the change automatically.
   - **Selected scripts/files only**: each selected item gets its own row in the mapping panel to edit. To change every name at once, use the two boxes below the mapping panel (e.g. `_DEV` → `_PROD`).
3. If any target already exists, pick a conflict option:
   - **Overwrite**: replaces the existing item
   - **Keep both (version)**: saves the new copy with a number on the end, e.g. `Main (2)`
4. Click **Promote**

**Note:** Promote copies within the BU you have open. To move scripts or files to a *different* BU, Export them here and Import them into the other BU.

**TO RENAME (Files only):**

Works like Promote, but moves the files instead of copying them.

1. Select the files or folders and click **Rename…**
2. Choose **Whole folder** (renames the folder in place, and removes the old folder once it is empty) or **Selected files only**
3. Edit the target paths, choose a conflict option if one appears, and click **Rename**

Items whose path did not change are skipped.

**TO EXPORT:**

1. Select the scripts/files and click **Export**
2. Choose a folder on your computer

A new subfolder named after the BU and the current date and time is created inside the chosen folder, so earlier exports are never overwritten. Scripts are saved as `.json` files; Files are saved as the original files. Folder structure is kept. Click **Cancel export** to stop an export in progress.

**TO IMPORT:**

1. Either:
   - Drag files or folders from File Explorer onto a folder in the browser (or onto the drop area below it to import into the selected folder), or
   - Click **browse…** in the drop area and choose **Files…** or **A folder…**
2. The **Review Import** panel opens. For each file you can:
   - Edit the **Save as** name
   - Use **Strip leading folders** to drop wrapper folders from the path (e.g. import the contents of `Export_2026\Scripts\` without those two folders)
   - Remove a whole drop with **×**
3. If any names already exist at the target, choose **Overwrite** or **Keep both (version)**
4. Click **Import**

You can drop several batches before importing; each one is listed separately. For Scripts, import the `.json` files produced by Export. For Files, any file type is uploaded as is.

**TO DUPLICATE:**

Select the scripts/files and click **Duplicate**. Each copy is saved in the same folder with ` (Copy)` added to its name (` (Copy 2)` and so on if a copy already exists).

**TO DELETE:**

Select the items and click **Delete**, then confirm. **This cannot be undone.**

- **Scripts**: selecting a folder deletes every script inside it
- **Files**: selected folders are deleted along with everything inside them. Empty folders can be selected and deleted on their own.

**FOR VARIABLE REDACTION (Scripts only):**

1. Select the scripts and click **Promote…**
2. In the **Variable Redaction** column, type a variable name and press **Enter** to add it. Repeat for each variable. Include `global:` as needed. Remove a variable with its **×**.
3. Click **Add redaction**

The redaction is applied to the selected scripts where they are. Nothing is promoted.

**Note:** This fully replaces any existing redaction on those scripts, so make sure your list includes every needed value, including existing ones. Allowed special characters are `, : - _`.
