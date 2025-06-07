# VALORANT Config Copier

A simple yet powerful command-line tool for easily copying VALORANT settings (crosshair, keybinds, graphics, etc.) from one account to another on the same computer. The script uses the [HenrikDev API](https://docs.henrikdev.xyz/) to fetch player names, making it easy to identify which profile belongs to which account.

## Demo

Here's what using the tool looks like:

```bash
$ node app.js
--- VALORANT Config Copier ---
HenrikDev API key found in your .env file.
Fetching player names using HenrikDev API...
? Select the SOURCE profile (copy settings FROM): (Use arrow keys)
❯ PlayerOne#EUW
  SmurfAccount#NA1
  FriendOnMyPC#EUW
? Select the DESTINATION profile (copy settings TO): (Use arrow keys)
  SmurfAccount#NA1
❯ FriendOnMyPC#EUW
? Are you sure you want to OVERWRITE the settings in SmurfAccount#NA1 with the settings from PlayerOne#EUW? This action cannot be undone. (y/N) y
Copying settings from PlayerOne#EUW to SmurfAccount#NA1...
✅ Success! Configs copied successfully.
```

## Features

- **Automatic profile detection:** Automatically finds all VALORANT user profiles in the default Windows installation path
- **Player name fetching:** Retrieves Riot ID (e.g., `PlayerName#TAG`) for each profile, so you know exactly which account you're working with
- **Interactive interface:** Clean, step-by-step menu guides you through the entire process
- **Safety confirmation:** Requires final confirmation before overwriting any files to prevent accidents
- **Secure API key storage:** Uses `.env` file to keep your API key secret and out of the script code

## Prerequisites

- [Node.js](https://nodejs.org/) (version 16.x or newer recommended)
- Windows operating system (script relies on the default `%localappdata%` path)

## Installation & Setup

Follow these steps to get the tool up and running.

### Step 1: Download the code

Clone this repository or download the source code as a ZIP file and extract it.

```bash
git clone <your-repository-url>
cd <project-folder-name>
```

### Step 2: Install dependencies

Open a terminal (such as Command Prompt, PowerShell, or Windows Terminal) in the project folder and run:

```bash
npm install
```

This command will install all necessary packages (inquirer, axios, colors, dotenv).

### Step 3: Get a HenrikDev API key

The script needs an API key to fetch player names.

1. Go to the [HenrikDev website](https://henrikdev.xyz/)
2. Sign in or create an account (you can use Discord, which is quick and easy)
3. After logging in, you should see your API key on the main page. It will look similar to `HDEV-xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`
4. Copy this key. Keep it secret and don't share it with anyone!

### Step 4: Configure your API key

1. In the project folder, find the file named `.env.example`
2. Create a copy of this file and rename the copy to `.env`
3. Open the new `.env` file with a text editor
4. Replace the example key with your real API key copied from the HenrikDev website

**Before (in .env.example file):**
```env
HENRIK_API_KEY=HDEV-xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
```

**After (in your new .env file):**
```env
HENRIK_API_KEY=HDEV-123ab45c-d67e-8f90-1234-56789abcdefg
```

## How to Use

Once setup is complete, running the tool is simple:

1. Open a terminal in the project folder
2. Run the script with the following command:
   ```bash
   node app.js
   ```
3. Follow the on-screen instructions to select your source and destination accounts

That's it! Your settings will be copied instantly.

## Config File Location

VALORANT configuration files are stored at:
```
C:\Users\YOUR_USERNAME\AppData\Local\VALORANT\Saved\Config
```

## Disclaimer

This is an unofficial third-party tool and is not affiliated with Riot Games. Use at your own risk. It's always good practice to manually backup your config folders before first using this tool.