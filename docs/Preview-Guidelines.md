[Back to Home](Readme.md) 

# About the Preview Environment
The AP Content API preview environment allows you to test new features and changes prior to the general release to ensure that they are properly handled by your client application. AP strongly recommends testing the changes in the preview environment before they become available in your production systems.

# Accessing the Preview Environment
To test API calls in the preview environment, you can follow the standard procedures described in the AP Content API Developer's Guide using the preview server URL and preview API key.

## Server URL
The AP Content API preview environment server URL is [https://apipreview.ap.org](https://apipreview.ap.org). 

## Preview API Key
A separate preview key is required for accessing the preview environment. If you have not received the preview key and would like to request access, please contact your AP Sales representative.

## Restricted Downloads
Intended as a testing platform, the preview environment provides restricted download access compared to the production environment. The main renditions of a content item (for example, high-resolution images) are not available for download in the preview environment. 

> _**Note**_: If the _showPricing=true_ parameter is specified in the request, the usage terms for all content items in the preview environment include the "860" use code:

```XML
<usageTerms role="apusecode:860">Not included in your plan. To learn more about license rights, please contact your licensing representative.</usageTerms>
```

[Back to Top](#about-the-preview-environment) 