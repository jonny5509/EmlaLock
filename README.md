# EmlaLock for Home Assistant

A Home Assistant custom integration for **EmlaLock**, including a bundled Lovelace card for displaying the current EmlaLock session and available actions.

> **Important:** EmlaLock remains responsible for account authentication, permissions, and server-side rules. This integration does not bypass those controls.

## ✨ Features

- 🏠 HACS-compatible Home Assistant custom integration
- ⚙️ Home Assistant Config Flow
- 🔐 EmlaLock account/API connection
- ☁️ Cloud polling
- 📡 Automatic discovery of EmlaLock entities
- 🎨 Bundled **EmlaLock Card**: `custom:emlalock-card`
- 🟢 Session active/inactive status
- 📅 Start and end dates
- ⏱️ Elapsed and remaining time
- ⏳ Minimum and maximum duration
- 🔗 Requirement links
- ➕ Add duration
- ➖ Subtract duration
- 🔑 Automatic detection of available holder-key actions
- 🔄 Automatic card registration after installation

## 📋 Requirements

- Home Assistant with support for custom integrations
- An EmlaLock account/API connection
- [HACS](https://hacs.xyz/) for the recommended installation method

## 📦 Installation

### HACS

1. Open **HACS → Integrations**.
2. Search for **EmlaLock**.
3. Install the integration.
4. Restart Home Assistant.
5. Go to **Settings → Devices & services → Add Integration**.
6. Search for **EmlaLock** and complete setup.

If the repository is not listed in HACS, add this repository as a custom repository:

`https://github.com/jonny5509/EmlaLock`

### Manual installation

1. Clone or download this repository.
2. Copy `custom_components/emlalock` into:
   `/config/custom_components/emlalock`
3. Restart Home Assistant.
4. Add **EmlaLock** from **Settings → Devices & services**.

## 🎨 EmlaLock Card

The repository includes a bundled Lovelace card:

`custom:emlalock-card`

The card is packaged in:

```text
dist/emlalock-card.js
```

The card can display:

- Current EmlaLock session information
- Active/inactive status
- Start and end dates
- Elapsed and remaining time
- Minimum and maximum duration
- Requirement links
- Duration controls
- Holder-key action availability

The card automatically discovers the EmlaLock entities created by the integration, so entity IDs do not need to be entered manually.

## 🖥️ Dashboard setup

The integration automatically installs, loads, and registers the bundled card.

To add it to a dashboard:

1. Open the dashboard you want to edit.
2. Select **Edit dashboard**.
3. Choose **Add card**.
4. Search for **EmlaLock Card**.
5. Add the card and save the dashboard.

### Home Assistant limitation

A custom integration cannot silently modify an existing user's dashboard and insert a card into it.

EmlaLock can automatically install, load, and register the card, but adding the card to an existing dashboard remains a dashboard UI action.

No manual `configuration.yaml` resource entry is required by this integration.

## 🔄 Updates

### HACS

After a HACS update:

1. Restart Home Assistant.
2. Reload the dashboard if the updated card is not immediately visible.

### Manual

Replace the installed integration/card files with the updated repository contents and restart Home Assistant.

If the card does not appear after an update, refresh the browser/dashboard.

## 🧪 Troubleshooting

### EmlaLock is not available

Check that:

- `custom_components/emlalock/` exists.
- Home Assistant has been restarted after installation.
- Your EmlaLock account/API configuration is valid.
- Home Assistant logs do not report an integration setup error.

### The card is not available

Check that:

- The integration is installed successfully.
- Home Assistant has been restarted after installation or update.
- The bundled card file is present.
- The browser/dashboard has been refreshed.

### The card cannot find entities

The card discovers entities created by the EmlaLock integration automatically.

Confirm that:

1. The integration is loaded.
2. EmlaLock entities are visible under **Settings → Devices & services**.
3. There are no setup errors in the Home Assistant logs.

## 🧑‍💻 Development

The integration source is under:

```text
custom_components/emlalock/
```

The bundled Lovelace card is maintained alongside the integration:

```text
dist/
www/
```

When developing changes, test both the Home Assistant integration and the Lovelace card after installation.

## 📁 Repository

Source code and issue tracking:

https://github.com/jonny5509/EmlaLock

## 📄 License

See [LICENSE](LICENSE) or the repository for the current project license.
