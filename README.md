# sshPilot plugins — discovery index

The curated index of third-party [sshPilot](https://github.com/mfat/sshpilot)
plugins. Each plugin is hosted in its author's own repository; this repo's
[`plugins.json`](plugins.json) lists them so they can be discovered and (soon)
installed from within sshPilot.

> Plugins run with full application privileges and are **not** sandboxed. Entries
> here are community-submitted and not vetted by the sshPilot maintainers —
> install only what you trust. sshPilot verifies each package's SHA-256 before
> installing and shows the plugin's declared permissions for consent.

## Add your plugin

1. Build from the
   [template](https://github.com/mfat/sshpilot-plugin-template) and publish a
   GitHub **release** with two assets: `your-plugin.zip` and
   `your-plugin.zip.sha256` (the archive's SHA-256).
2. Open a PR adding an entry to `plugins.json` (see the format in the
   [registry docs](https://github.com/mfat/sshpilot/blob/main/docs/plugins/registry.md)):

```json
{
  "id": "your-plugin",
  "name": "Your Plugin",
  "description": "One-line summary.",
  "author": "you",
  "homepage": "https://github.com/you/your-plugin",
  "latestVersion": "1.0.0",
  "versions": [
    {
      "version": "1.0.0",
      "api_version": 1,
      "permissions": ["network"],
      "package": {
        "downloadUrl": "https://github.com/you/your-plugin/releases/download/v1.0.0/your-plugin.zip",
        "checksumUrl": "https://github.com/you/your-plugin/releases/download/v1.0.0/your-plugin.zip.sha256"
      }
    }
  ]
}
```

See the [plugin developer guide](https://github.com/mfat/sshpilot/blob/main/docs/plugins/writing-plugins.md).
