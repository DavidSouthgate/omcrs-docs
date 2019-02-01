# Config
Different deployments of the app can have config specific to that
deployment. This allows for application branding to change whilst
maintaining the same codebase.

This config file is located in `/config/config.json`

An example of this file is shown below:
```
{
  "server": "https://example.com/",
  "color": {
    "primary": "000000",
    "primaryText": "ffffff",
    "hover": "eeeeee"
  },
  "logo": {
    "wide": "logo-wide.png",
    "narrow": "logo-narrow.png"
  }
}
```

| server            |                   |
|-----|-----|
| server                | The URL of the OMCRS web application deployment
| color > primary       | The primary hex color of the application (optional)
| color > primaryText   | The primary text color of the application (optional)
| color > hover         | The color used for when hovering (optional)
| logo > wide           | Wide logo file. Displayed on splash screen if specified (optional)
| logo > narrow         | Narrow logo file. Displayed on live view if specified (optional)