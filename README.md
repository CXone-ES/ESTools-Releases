## 🛠️ Setup & Installation
- Download the latest version of the Setup.exe from Releases.
- Open a terminal and run this command:
```bash
npx playwright install
```
- Create a User profile

## ➕ Creating User Profiles
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



## 🛣️ Roadmap

- Support FedRamp and non-TMA Accounts
