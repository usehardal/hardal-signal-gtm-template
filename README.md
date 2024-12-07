![Static Badge](https://img.shields.io/badge/Hardal-SDK-8A2BE2)


<p align="center">
  <a href="https://usehardal.com/" target="_blank">
    <img src="https://res.cloudinary.com/hardal/image/upload/v1733595875/fkqkxwagpfukvthci9ny.svg" alt="Hardal" width="180" height="84">
  </a>
</p>


# Hardal Signal SDK Google Tag Manager Template

Hardal is a client-side to server-side event collection enhancer designed for first-party endpoints. This Google Tag Manager template enables seamless integration of Hardal server-side capabilities into your website.

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

## Usage

### Basic Setup

```jsx
javascript
Copy
// Initialize Hardal with basic configuration
window.hardalConfig = {
    options: {
        autoPageview: true,
        fetchFromGA4: true,
        fetchFromFBPixel: true,
    }
};

```

### Custom Event Tracking

```jsx

// Track a custom event
window.hardal.track('custom_event', {
    category: 'user_action',
    action: 'button_click',
    label: 'submit_form'
});

```

### Manual Pageview Tracking

```jsx

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
