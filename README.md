# AWTRIX NG Birthdays

Birthday countdown app for AWTRIX NG with age display, birthday cake, animated countdown bar, optional rainbow text and a browser-based birthday editor.

The editor runs entirely inside the browser. Names and birthdays are not uploaded to a server.

## Features

- upcoming birthdays appear during a configurable number of days
- displays the age the person will turn
- birthday cake icon with a built-in fallback drawing
- animated seven-segment countdown bar
- optional rainbow animation on the birthday
- German and English settings
- bilingual browser editor (German/English) with JSON and CSV import
- export of a ready-to-use `birthday_data` module
- downloadable offline editor for direct transfer to an AWTRIX NG in the local network

## Installation

### 1. Add or import birthdays

Open the [AWTRIX Birthday Editor](https://pacroy9.github.io/awtrix-ng-birthdays/).

Select **Deutsch** or **English** in the top-right corner. Add the birthdays manually or import a compatible JSON or CSV file. The editor stores the working list only in the current browser.

Now choose one of the following installation methods.

### 2A. Direct transfer with the offline editor (recommended)

The hosted editor cannot reliably connect from its secure HTTPS page to an AWTRIX device using local HTTP. Therefore direct transfer is intentionally available only in the downloaded offline editor.

1. In the online editor, click **Offline-Editor herunterladen** / **Download offline editor**.
2. Open the downloaded `birthday-editor.html` with a double-click. The current birthday list is included automatically.
3. Enter the local AWTRIX address, for example `192.168.20.99`.
4. Enter the app script name shown under **Scripts**, for example `geburtstage`. Do not enter the display name `Birthdays` or the module name `birthday_data`.
5. Click **Verbindung testen** / **Test connection**.
6. Click **An AWTRIX übertragen** / **Send to AWTRIX**.

The transfer replaces the complete `birthday_data` module and reloads the birthday app. Keep a JSON backup before making larger changes. If the browser still blocks local access, use the manual method below. Do not disable browser security features.

### 2B. Manual module installation

In the online or offline editor, click **AWTRIX-Modul herunterladen** / **Download AWTRIX module**.

The editor creates `birthday_data.berry`.

Install or replace the module:

1. Open the AWTRIX NG web interface.
2. Open **Scripts**.
3. Under **Modules**, click **+**.
4. Use the exact module name `birthday_data`.
5. Paste the complete contents of the exported `birthday_data.berry` file.
6. Save the module.

The module must be installed before the main script. Otherwise AWTRIX reports `module 'birthday_data' not found`.

### 3. Install the app script

Install `Birthdays.berry` from this repository as an AWTRIX NG script. When publishing through the AWTRIX Hub, the Hub version can be installed directly after the data module has been created.

### 4. Configure the app

Open **Apps**, locate **Birthdays**, and use the gear button to configure:

- language
- standard text color
- rainbow text on the birthday
- number of countdown days
- handling of 29 February in non-leap years
- decorative sparkle animation

## Updating birthdays

Open the online editor again and import the previously saved JSON backup if necessary. Edit the list and either download a fresh offline editor for direct transfer or export a new `birthday_data.berry` for manual installation. Direct transfer reloads the main app automatically; after a manual module update, reload or save the main app script once.

## Data format

Each entry uses this format:

```berry
["NAME", YEAR, MONTH, DAY]
```

Example:

```berry
["EXAMPLE", 2000, 1, 1]
```

## Files

- `Birthdays.berry` — AWTRIX NG application script
- `birthday_data.example.berry` — non-personal example module
- `index.html` — online editor and downloadable offline editor in one file

## Privacy

The editor stores its working list in the browser's local storage. When the offline editor is downloaded, the current list is embedded in that local HTML file. Direct transfer communicates only with the AWTRIX address entered by the user. No birthday data is uploaded to this repository or to the editor host.

## License

MIT
