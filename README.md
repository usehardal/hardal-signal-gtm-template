<p align="center">
  <a href="https://usehardal.com/">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://imge.usehardal.com/cdn/logo/new/svg/hnav0hronsb1fttdnmph.svg?raw=1">
      <source media="(prefers-color-scheme: light)" srcset="https://imge.usehardal.com/cdn/logo/new/svg/ptlior6hfvknmblekenh.svg?raw=1">
      <img src="https://imge.usehardal.com/cdn/logo/new/svg/ptlior6hfvknmblekenh.svg?raw=1" alt="Hardal" width="180">
    </picture>
  </a>
</p>

# Hardal Signal Tag for Google Tag Manager

Load the Hardal Signal browser collector through a Google Tag Manager (GTM) **web container** to send website events to your Hardal endpoint. The template creates the collector configuration and loads `{endpoint}/hardal`, with pageview, GA4, Meta Pixel, and data layer options.

## Getting started

You need a GTM web container and a compatible Hardal Signal endpoint. Import the tag template, configure the fields below, and choose when the collector should load.

## Features

- Automatic pageview tracking
- Integration with Google Analytics 4 params collection
- Meta Pixel integration for enhanced tracking capabilities
- Cookieless tracking support
- Custom event tracking
- Data Layer integration

## Installation

1. In Google Tag Manager, go to **Templates** > **Tag Templates** > **New**
2. Click on **Import** and select [hardal-signal.tpl](hardal-signal.tpl)
3. Save the template and create a tag using it.
4. Configure the fields below, add a page-loading trigger appropriate to your integration, and check it in GTM Preview before publishing.

## Configuration

### Required fields

- **Container ID**: Your unique Hardal container identifier
- **Endpoint URL**: The URL of your Hardal API endpoint

### Optional settings

- **Auto Pageview**: Enable/disable automatic page view tracking (default: enabled)
- **Fetch from Google Analytics 4**: Enable/disable GA4 integration for client/session ID and consent state (GCS) collection (default: enabled)
- **Fetch from Meta Pixel**: Enable/disable Meta Pixel integration (default: enabled)
- **Fetch from dataLayer**: Enable/disable data layer integration

### Current template behavior

The template's JavaScript uses `value || true` for all four checkbox settings, so unchecked boxes are currently passed as `true`. The Container ID field is present in the UI but is not forwarded into `hardalConfig`. The script-injection permission currently allows `https://*.usehardal.com/*`; custom domains require the appropriate GTM template permission.

See [the template source](hardal-signal.tpl) for the configuration and permission contract.

## Usage

### Basic setup

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

### Custom event tracking

```js

// Track a custom event
window.hardal.track('custom_event', {
    category: 'user_action',
    action: 'button_click',
    label: 'submit_form'
});

```

### Manual pageview tracking

```js

// Manually track a pageview
window.hardal.trackPageview();

```

## Event data collection

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

## Browser support

Supports all modern browsers including:

- Chrome
- Firefox
- Safari
- Edge
- Mobile browsers

## Version information

README version: 1.0.2.1. See [hardal-signal.tpl](hardal-signal.tpl) for the current template implementation.

## Support

Maintained by [Hardal](https://github.com/usehardal).

- [Hardal documentation](https://docs.usehardal.com)
- [Report an issue](https://github.com/usehardal/hardal-signal-gtm-template/issues)
- [Hardal website](https://usehardal.com)

