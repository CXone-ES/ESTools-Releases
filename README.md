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

- `C:\Users\{Your UserName}\AppData\Local\Google\Chrome\User Data\{Profile #}\Extensions\ppnbnpeolgkicgegkbkbjmhlideopiji\1.0.##_#`
- To ensure it's the correct extension, look inside the `1.0.##_#` folder - you should see multiple windows PNGs and a `manifest.json` (required)

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
6. Click the Studio button to copy the token

**Refreshing or Switching Tenants:**

- To refresh or switch tenants, click on your User and the process will restart, providing you with the list of tenants to select from

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

## 📜 Script Management

**Accessing Script Management:**

In your selected BU, click "Scripts" to open the script pane.

**Navigating the Script Pane:**

- Your BU selection will show at the top of the page
- You can filter scripts using the search bar under the BU selection
- The back button will take you back to the BU/BU search screen (depending on if it's in TMA)

**Selecting Scripts:**

Existing scripts are listed in the left pane. Click the checkbox by each script you would like to update.

**TO PROMOTE:**

1. Enter the previous environment in the "Replace What" box
2. Enter your new environment in the "Replace With" box
3. Click the "Submit" button

**Note:** The way the APIs work, the folder path is directly appended to the script name. So you can replace either folders or script names here. You can include extra characters like the `_` or `\` if you're worried about the replace function matching where it shouldn't.

A loading bar appears at the bottom to show progress, and the results of each update will appear in logs.

**FOR VARIABLE REDACTION:**

1. In the redaction text box, enter the full list of variables as a comma-separated list (no spaces are necessary)
2. Include "global:" as needed

**Note:** This will fully replace any existing redaction, so ensure your list includes all needed values including existing ones.

## Tech Stack

- **Electron** (with Electron Forge)
- **React** (UI)
- **Playwright** (SSO automation)
- **Node.js** backend with secure IPC
- **CXone API** integration (using access tokens)
