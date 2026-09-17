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
- browser editor with JSON and CSV import
- export of a ready-to-use `birthday_data` module
- optional direct transfer to an AWTRIX NG in the local network

## Installation

### 1. Create the birthday data module

Open the [AWTRIX Birthday Editor](https://pacroy9.github.io/awtrix-ng-birthdays/).

Add the birthdays manually or import a compatible JSON or CSV file. Then click **AWTRIX-Modul herunterladen**.

The editor creates `birthday_data.berry`.

### 2. Install the module

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

Open the editor again, import the previously saved JSON backup if necessary, edit the list and export or transfer a new `birthday_data.berry` module. Reloading the main script makes the changed list available immediately.

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
- `index.html` — browser editor published with GitHub Pages

## Privacy

The editor stores its working list in the browser's local storage. Direct transfer communicates only with the AWTRIX address entered by the user. No birthday data is sent to this repository or to the editor host.

## License

MIT
