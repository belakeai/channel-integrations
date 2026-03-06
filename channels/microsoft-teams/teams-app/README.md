# Deploy Belake as a Microsoft Teams App

## Overview

- **What it does**: Adds Belake as a personal tab in Microsoft Teams so users can access the Belake portal without leaving Teams.
- **When to use**: When your organization uses Teams and wants Belake accessible as a native app.

## Prerequisites

- Microsoft 365 tenant with Teams
- Belake.ai account with your portal URL configured
- App URL must be HTTPS and accessible from your tenant
- Admin rights to upload apps to your Teams tenant (for organization-wide deployment), or sideload for testing

## Steps

### 1. Configure the manifest

Edit `manifest.json` and replace the placeholders with your environment values:

| Field | Replace with |
|-------|--------------|
| `staticTabs[0].contentUrl` | Your Belake portal URL |
| `staticTabs[0].websiteUrl` | Your Belake portal URL |
| `validDomains` | Domains hosting your Belake portal (e.g., `your-domain.com`) |
| `id` | A unique GUID for your app (use a [GUID generator](https://www.guidgenerator.com/)) |
| `name.short`, `name.full` | Your app display name |
| `description.short`, `description.full` | Your app description |

### 2. Add icons

Place `color.png` (192×192) and `outline.png` (32×32) in the same folder as `manifest.json`, or reference them via URL in the manifest if your hosting supports it.

### 3. Package the app

```bash
zip -r belake-teams-app.zip manifest.json color.png outline.png
```

### 4. Upload to Teams

1. Open Microsoft Teams
2. Go to **Apps** → **Manage your apps** → **Upload a custom app**
3. Select the `belake-teams-app.zip` file
4. The app will appear in **Apps** for users to add as a personal tab

### 5. Validate before publishing

Use the [Teams App Validator](https://dev.teams.microsoft.com/validation) to validate the package before upload.

## Configuration

| Setting | Description |
|---------|-------------|
| Belake portal URL | HTTPS URL of your Belake instance (from your Belake dashboard) |
| Valid domains | Domains that host your Belake portal; must match Teams manifest requirements |
| App ID | Unique GUID for your Teams app (required for production) |

**Have questions about the manifest structure?** See [sample-data.json](./sample-data.json) for a complete example with all fields populated.

## Troubleshooting

- **Blank tab**: Ensure your Belake URL allows iframe embedding and that your domain is listed in `validDomains`.
- **Upload errors**: Verify manifest schema and that all required fields are present. Use the Teams App Validator.
- **Auth issues**: Ensure SSO or login flow works when launched from Teams.

## Next Steps

- [Deploy as Copilot Studio Agent](../copilot-studio-agent) *(coming soon)*
- [Microsoft Teams App Manifest Schema](https://learn.microsoft.com/en-us/microsoftteams/platform/resources/schema/manifest-schema)
