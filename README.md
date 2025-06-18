## 🛠️ Setup & Installation
Quick Setup Guide

https://github.com/user-attachments/assets/29cdc811-a24b-461e-8696-3282c85e37a7
- Download the latest version of the Setup.exe from Releases.
- Open a terminal and run this command:
```bash
npx playwright install
```
- Create a User profile

## ➕ Creating User Profiles

![create_user](https://github.com/user-attachments/assets/2702ca46-a1ad-4e8d-a23f-24e8941edff4)

Chrome Profiles and Microsoft SSO extension paths are required in or for this app to work. This will work with your default work profile but if you want to create a new profile/don't have a profile the instructions can be found here: https://support.google.com/chrome/answer/2364824?hl=en&co=GENIE.Platform%3DDesktop

Once you have a profile you would like to use, you will need to know the path to both the profile and the Microsoft SSO extension in order to add a User.

The typical path to the profile is:
- C:\Users\\{Your UserName}\AppData\Local\Google\Chrome\User Data\Default || {Profile #}

For the Microsoft SSO extension:
- C:\Users\\{Your UserName}\AppData\Local\Google\Chrome\User Data\{Profile #}\Extensions\ppnbnpeolgkicgegkbkbjmhlideopiji\1.0.##_#
- To ensure its the correct extension look inside the 1.0.##_# folder you should see multiple windows PNGs and a manifest.json (required)

With a profile and the locations of the two folder you will be ready to create a User by pressing the Add User button and completing the form.

Profile data is stored locally on your machine at:
- C:\Users\\{Your UserName}\AppData\Roaming\estools\config.json

## 🔍 Search Accounts

![search](https://github.com/user-attachments/assets/7b235297-40cb-45f5-ad30-f57d87130a33)

- Click on User
- Wait for the the accounts to load, you will see a Chromium window pop up which will be automating the login process.
- After tenants load, select a tenant
- After the search bar appear on the right, enter in either a full BU # or a full or partial account name
- Press enter or hit search
- Press the Studio button to copy the token
- If you need to refresh or switch tenants, press on your User and the process will restart and provide you the list of tenants to select from

## 🛣️ Roadmap

- Support FedRamp and non-TMA Accounts
