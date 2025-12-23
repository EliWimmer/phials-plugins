# Phials Community Plugins

This repository is the central registry for community plugins for [Phials](https://github.com/phials-dev/phials).

## For Users

Browse and install community plugins directly from within Phials:

1. Open Phials
2. Go to **Settings** → **Plugins**
3. Switch to the **Community** tab
4. Browse or search for plugins
5. Click **Install** to add a plugin

## For Plugin Developers

### Creating a Plugin

1. Create a new repository for your plugin
2. Structure your plugin with the following files:
   - `manifest.json` - Plugin metadata
   - `main.js` - Bundled plugin code (ES module)
   - `styles.css` (optional) - Custom styles

### manifest.json Schema

```json
{
  "id": "your-username.plugin-name",
  "name": "Your Plugin Name",
  "version": "1.0.0",
  "minAppVersion": "0.1.0",
  "author": "Your Name",
  "description": "A brief description of your plugin",
  "authorUrl": "https://github.com/your-username",
  "repository": "https://github.com/your-username/phials-plugin-name",
  "icons": ["mdi:icon-name"],
  "permissions": ["filesystem.read"]
}
```

#### Required Fields

| Field | Description |
|-------|-------------|
| `id` | Unique identifier in format `vendor.plugin-name` (lowercase, alphanumeric with hyphens) |
| `name` | Human-readable display name |
| `version` | Semver version string (e.g., "1.0.0") |
| `minAppVersion` | Minimum Phials version required |
| `author` | Plugin author name |
| `description` | Brief description (shown in plugin browser) |

#### Optional Fields

| Field | Description |
|-------|-------------|
| `authorUrl` | Link to author's website or profile |
| `repository` | GitHub repository URL |
| `icons` | Array of Iconify icon names to preload |
| `permissions` | Array of required permissions |

### Available Permissions

| Permission | Description | Risk Level |
|------------|-------------|------------|
| `filesystem.read` | Read files from the filesystem | Low |
| `filesystem.write` | Write and delete files | High |
| `clipboard.read` | Read clipboard content | Medium |
| `clipboard.write` | Write to clipboard | Low |
| `shell.execute` | Execute shell commands | High |
| `network.fetch` | Make network requests | Medium |

### Creating a Release

1. Build your plugin to produce `main.js`
2. Create a GitHub Release with the following assets:
   - `manifest.json`
   - `main.js`
   - `styles.css` (if applicable)
3. Tag the release with a version number (e.g., `v1.0.0` or `1.0.0`)

### Submitting to the Community Registry

1. Fork this repository
2. Add your plugin to `community-plugins.json`:

```json
{
  "id": "your-username.plugin-name",
  "name": "Your Plugin Name",
  "author": "Your Name",
  "description": "A brief description",
  "repo": "your-username/phials-plugin-name"
}
```

3. Submit a Pull Request
4. Wait for review and approval

### Guidelines

- **Security**: Only request permissions your plugin actually needs
- **Quality**: Test your plugin thoroughly before submitting
- **Documentation**: Include a README in your plugin repository
- **Updates**: Create new GitHub Releases for updates

## Plugin Development Resources

- [Plugin Template](https://github.com/phials-dev/phials-plugin-template) - Starter template with build configuration
- [PDF Plugin Example](https://github.com/phials-dev/phials-plugin-pdf) - Reference implementation
- [Plugin API Documentation](https://github.com/phials-dev/phials/blob/main/docs/plugin-api.md)

## License

MIT
