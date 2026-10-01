<p align="center">
  <a href="https://usehardal.com/">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://imge.usehardal.com/cdn/logo/new/svg/hnav0hronsb1fttdnmph.svg?raw=1">
      <source media="(prefers-color-scheme: light)" srcset="https://imge.usehardal.com/cdn/logo/new/svg/ptlior6hfvknmblekenh.svg?raw=1">
      <img src="https://imge.usehardal.com/cdn/logo/new/svg/ptlior6hfvknmblekenh.svg?raw=1" alt="Hardal" width="180">
    </picture>
  </a>
</p>

![Static Badge](https://img.shields.io/badge/Hardal-SDK-8A2BE2)

# Hardal Signal SDK Google Tag Manager Template

Hardal Signal sends first-party event data from your website to a server-side endpoint. This Google Tag Manager template loads the Hardal collector and provides pageview, GA4, Meta Pixel, and data layer options.

## Features

- Automatic pageview tracking
- Integration with Google Analytics 4 params collection
- Meta Pixel integration for enhanced tracking capabilities
- Cookieless tracking support
- Custom event tracking
- Data Layer integration

## Installation

1. In Google Tag Manager, go to **Templates** > **Tag Templates** > **New**
2. Click on **Import** and select the Hardal template file
3. Save the template

## Configuration

### Required Fields

- **Container ID**: Your unique Hardal container identifier
- **Endpoint URL**: The URL of your Hardal API endpoint

### Optional Settings

- **Auto Pageview**: Enable/disable automatic page view tracking (default: enabled)
- **Fetch from Google Analytics 4**: Enable/disable GA4 integration for client/session ID and consent state (GCS) collection (default: enabled)
- **Fetch from Meta Pixel**: Enable/disable Meta Pixel integration (default: enabled)
- **Fetch from dataLayer**: Enable/disable data layer integration

## Usage

### Basic Setup

```js
// Initialize Hardal with basic configuration
window.hardalConfig = {
    endpoint: 'https://YOUR_HARDAL_ENDPOINT',
    options: {
        autoPageview: true,
        fetchFromGA4: true,
        fetchFromFBPixel: true,
    }
};

```

### Custom Event Tracking

```js

// Track a custom event
window.hardal.track('custom_event', {
    category: 'user_action',
    action: 'button_click',
    label: 'submit_form'
});

```

### Manual Pageview Tracking

```js

// Manually track a pageview
window.hardal.trackPageview();

```

## Event Data Collection

Hardal automatically collects:

- Page information (URL, title, referrer)
- Browser details
- Device information
- Screen resolution
- Performance metrics
- UTM parameters
- User consent status
- GA4 data (when enabled)
- Meta Pixel data (when enabled)

## Browser Support

Supports all modern browsers including:

- Chrome
- Firefox
- Safari
- Edge
- Mobile browsers

## Version Information

Current Version: 1.0.2.1

## Support

For technical support or feature requests, please submit an issue in the repository or contact the Hardal support team.
