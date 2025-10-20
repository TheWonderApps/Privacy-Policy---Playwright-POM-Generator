# Privacy Policy - Playwright POM Generator


---

## Overview

Playwright POM Generator is a Chrome extension that generates Playwright Page Object Model code from webpages. We are committed to protecting your privacy and being transparent about our practices.

**Bottom line: We do NOT collect, store, or transmit ANY user data.**

---

## Data Collection

### What We DON'T Do ❌

- ❌ **No analytics or tracking** - We don't use Google Analytics, Mixpanel, or any tracking service
- ❌ **No user accounts** - No registration, login, or authentication required
- ❌ **No server-side storage** - We don't have servers storing your data
- ❌ **No third-party services** - No external APIs, CDNs, or cloud services
- ❌ **No external network calls** - Extension never communicates with the internet
- ❌ **No personal information** - We never collect names, emails, or identities
- ❌ **No browsing history** - We don't track which websites you visit
- ❌ **No page content transmission** - Page data stays on your device
- ❌ **No crash reporting** - No error logs sent to external services
- ❌ **No advertising** - No ad networks or tracking pixels

### What the Extension Does ✅

- ✅ **Reads page structure** - Only when you click "Analyze Current Page" button
- ✅ **Local processing** - All DOM analysis happens in your browser
- ✅ **Local storage** - Saves preferences using `chrome.storage.local` (never transmitted)
- ✅ **Local history** - Keeps last 20 generated POMs on your device (never uploaded)

**Everything happens locally. Nothing leaves your browser.**

---

## Permissions Explanation

The extension requests these permissions from Chrome. Here's why each is needed:

### 1. `activeTab` Permission

**What it allows:**  
Access to read the content of the currently active tab

**Why we need it:**  
To analyze page structure (DOM) and identify interactive elements (buttons, inputs, forms) when you click "Analyze Current Page"

**When it's used:**  
Only when you explicitly click the "Analyze Current Page" button

**Privacy impact:**  
Minimal - we only read page structure, never transmit it anywhere

---

### 2. `scripting` Permission

**What it allows:**  
Inject JavaScript code into web pages

**Why we need it:**  
Required by Manifest V3 to programmatically inject our content script that scans the page for elements

**When it's used:**  
Only when you click "Analyze Current Page"

**Privacy impact:**  
None - the injected script only reads DOM structure and runs locally

---

### 3. `storage` Permission

**What it allows:**  
Store data locally using `chrome.storage.local`

**Why we need it:**  
To remember your preferences across browser sessions:

- Language preference (TypeScript/Python)
- Naming convention (camelCase, snake_case, PascalCase)
- Locator strategy (semantic-first, CSS-first, testid-only)
- Theme preference (dark/light mode)
- History of last 20 generated POMs

**Privacy impact:**  
None - all data is stored locally on your device, never synchronized or transmitted

---

### 4. `sidePanel` Permission

**What it allows:**  
Display extension interface in Chrome's side panel

**Why we need it:**  
To show the generated code and extension controls in a non-intrusive way

**Privacy impact:**  
None - purely for UI display

---

### 5. `<all_urls>` Host Permission

**What it allows:**  
Run content script on any website

**Why we need it:**  
The tool is designed to work on ANY website (development, testing, production environments). QA engineers and developers need to analyze pages across many different domains.

**Limitations:**

- Only active when you explicitly click "Analyze" button
- Automatically blocked on restricted pages (chrome://, edge://, etc.)
- No background monitoring or automatic injection
- No data transmission from analyzed pages

**Alternative considered:**  
Requesting permission per-domain would severely harm usability and workflow

**Privacy impact:**  
Controlled - only reads page structure on user command, never transmits data

---

## Data Storage Details

### What We Store Locally

The extension uses `chrome.storage.local` (Chrome's local storage API) to save:

1. **User Preferences:**

   - `language`: "typescript" or "python"
   - `namingConvention`: "camelCase", "snake_case", or "PascalCase"
   - `includeComments`: boolean
   - `includeAssertions`: boolean
   - `groupBySection`: boolean
   - `locatorStrategy`: "semantic-first", "css-first", or "testid-only"
   - `theme`: "light" or "dark"

2. **Session History:**
   - Last 20 generated POM files with metadata
   - Each entry includes: timestamp, page URL, generated code, language used
   - Automatically limited to 20 items (oldest removed when limit reached)

### Where Data is Stored

- **Location:** Your local Chrome profile directory
- **Access:** Only this extension can read it
- **Synchronization:** NOT synced to your Google account
- **Transmission:** NEVER sent to any server

### How to Clear Data

You can clear all stored data at any time:

1. **Via Chrome Settings:**

   - Go to `chrome://extensions/`
   - Find "Playwright POM Generator"
   - Click "Remove" to uninstall (removes all data)

2. **Via Chrome Storage:**

   - Open DevTools (F12)
   - Go to Application → Storage → Extension Storage
   - Manually clear `chrome.storage.local`

3. **Via Extension UI:**
   - History can be cleared from the extension's history panel

---

## Third-Party Services

**We do NOT use ANY third-party services:**

- ❌ No Google Analytics
- ❌ No Firebase
- ❌ No Sentry/Bugsnag (crash reporting)
- ❌ No advertising networks
- ❌ No CDNs for loading libraries
- ❌ No backend servers
- ❌ No databases
- ❌ No cloud storage

**All JavaScript libraries are bundled with the extension. No external scripts loaded.**

---

## Security Measures

### Content Security Policy (CSP)

We implement a strict Content Security Policy:

```json
"content_security_policy": {
  "extension_pages": "script-src 'self'; object-src 'self'"
}
```

This prevents:

- Loading external scripts
- Inline script execution
- Code injection attacks
- XSS vulnerabilities

### Safe Coding Practices

- ✅ No `eval()` or `Function()` constructors
- ✅ No inline event handlers
- ✅ Proper input sanitization
- ✅ Safe innerHTML usage (only for UI rendering, not user input)
- ✅ No dangerous APIs

### Code Transparency

Our extension is **100% open source**. You can review every line of code at:

**GitHub Repository:** https://github.com/TheWonderApps/Playwright-POM-Generator

### Data Encryption

Since data is stored locally using Chrome's storage API:

- Chrome handles encryption of local storage
- Data at rest is protected by Chrome's security model
- No transmission means no need for encryption in transit

---

## Your Rights & Control

### Data Access

Since we don't collect any data, there's no data for you to:

- Request access to
- Request a copy of
- Request correction of
- Request deletion of

All data is stored locally on YOUR device under YOUR control.

### Opt-Out

If you don't want the extension to store preferences locally:

- Simply don't use the extension, or
- Uninstall it (removes all local data)

### Data Portability

Your generated code is yours:

- Download as `.ts` or `.py` files
- Copy to clipboard
- No lock-in to our extension

---

## Children's Privacy

The extension does not knowingly collect data from anyone, including children under 13. Since we don't collect any data at all, COPPA compliance is inherently maintained.

---

## International Users

The extension works the same globally:

- No geo-specific tracking
- No location-based data collection
- GDPR compliant by design (no data processing)
- CCPA compliant (no data sale)

---

## Changes to This Policy

We may update this privacy policy occasionally to reflect:

- Extension feature changes
- Legal or regulatory updates
- User feedback

**Changes will be noted with an updated "Last Updated" date.**

Significant changes will be communicated via:

- Chrome Web Store extension description
- GitHub repository release notes

---

## Cookies and Tracking Technologies

**We do NOT use:**

- ❌ Cookies
- ❌ Web beacons
- ❌ Fingerprinting
- ❌ Local storage for tracking
- ❌ Session storage for tracking
- ❌ ETags or cache-based tracking
- ❌ Any tracking mechanisms

The only browser storage we use is `chrome.storage.local` for saving YOUR preferences on YOUR device.

---

## Automated Decision-Making

The extension does not use:

- ❌ Artificial Intelligence for data processing
- ❌ Machine learning on user data
- ❌ Automated profiling
- ❌ Behavioral analytics

The code generation algorithm only analyzes page DOM structure (not user behavior).

---

## Data Breach Notification

Since we don't collect or store user data on servers:

- **No data breach risk** - We have no user database to breach
- **Local data security** - Managed by Chrome's security model
- **No notification needed** - No user data to compromise

If a security issue is discovered in the extension code itself, we will:

1. Release a patched version immediately
2. Post security advisory on GitHub
3. Update Chrome Web Store listing
4. Notify users via extension update

---

## Data Retention Policy

**User Preferences:** Retained until you uninstall the extension or clear Chrome data

**Session History:** Last 20 generated POMs retained locally, automatically rotated (oldest deleted when limit reached)

**Generated Code:** Not retained by the extension (only if you save locally to history)

**Deletion:** All data is permanently deleted when you uninstall the extension

---

## Third-Party Links

The extension may generate code that references external documentation (e.g., Playwright official docs). We are not responsible for the privacy practices of external websites.

---

## Contact Information

For privacy concerns, questions, or feedback:

- **GitHub Issues:** https://github.com/TheWonderApps/Playwright-POM-Generator/issues
- **Repository:** https://github.com/TheWonderApps/Playwright-POM-Generator
- **Developer:** TheWonderApps ([@TheWonderApps](https://github.com/TheWonderApps))

We typically respond within 48 hours.

---

## Legal Compliance

### General Data Protection Regulation (GDPR)

The extension complies with GDPR because:

- We don't process personal data
- We don't transfer data outside your device
- We don't profile users
- Users have full control over local data

### California Consumer Privacy Act (CCPA)

The extension complies with CCPA because:

- We don't sell personal information
- We don't collect personal information
- We don't share data with third parties

### Other Regulations

Since we don't collect data, we inherently comply with most data protection regulations worldwide, including:

- **PIPEDA (Canada)** - No personal information collected
- **LGPD (Brazil)** - No personal data processing
- **PDPA (Singapore)** - No personal data collection
- **Privacy Act (Australia)** - No personal information handling
- **UK GDPR** - Same as EU GDPR compliance

---

## Business Transfers

In the unlikely event of:

- Sale of the extension
- Merger with another company
- Bankruptcy or dissolution

**Your privacy is still protected because:**

- We have no user data to transfer
- All data remains locally on your device
- New owners cannot access your local data
- You can uninstall at any time

---

## Compliance Certifications

While we don't have formal certifications (not required for extensions with zero data collection), our practices align with:

- ✅ **ISO 27001** principles (information security)
- ✅ **Privacy by Design** principles
- ✅ **NIST Privacy Framework** (no data collection = no privacy risk)
- ✅ **Chrome Web Store Developer Program Policies**

---

## User Responsibilities

While we protect your privacy, you are responsible for:

- Reviewing generated code before using in production
- Not including sensitive data in generated code comments
- Securing downloaded files on your local system
- Managing your Chrome browser security settings

---

## Summary

**Playwright POM Generator is designed with privacy as a core principle:**

✅ **No data collection**  
✅ **No external communication**  
✅ **No third-party services**  
✅ **100% local processing**  
✅ **Open source code**  
✅ **Full user control**

**Your privacy is protected because we simply don't collect any data at all.**

---

## Acknowledgment

By installing and using Playwright POM Generator, you acknowledge that:

1. You have read this privacy policy
2. You understand that the extension processes data locally only
3. You understand that no data is transmitted to external servers
4. You can uninstall the extension at any time to remove all local data

---

**Last Updated:** October 20, 2025  
**Policy Version:** 1.1  
**Extension Version:** 1.0.7  
**Developer:** TheWonderApps

---

## Version History

| Version | Date         | Changes                                                                                                           | Extension Version |
| ------- | ------------ | ----------------------------------------------------------------------------------------------------------------- | ----------------- |
| 1.1     | Oct 20, 2025 | Enhanced with additional compliance sections, data breach notification, automated decision-making, cookies policy | 1.0.7             |
| 1.0     | Oct 20, 2025 | Initial comprehensive privacy policy                                                                              | 1.0.7             |

---

## Privacy Policy URL

This privacy policy is hosted at:

- **GitHub:** https://github.com/TheWonderApps/Playwright-POM-Generator/blob/main/PRIVACY_POLICY.md
- **GitHub Pages:** https://thewonderapps.github.io/Playwright-POM-Generator/PRIVACY_POLICY.html _(coming soon)_

---

## Attestation

**Developer Statement:**

I, as the developer of Playwright POM Generator, attest that:

1. This extension does not collect any user data
2. This extension does not transmit any data to external servers
3. All data processing occurs locally in the user's browser
4. All permissions are used only for stated purposes
5. The extension complies with Chrome Web Store policies
6. The source code is publicly available for audit

**Signed:** TheWonderApps  
**Date:** October 20, 2025

---

_This privacy policy is effective as of October 20, 2025 and applies to version 1.0.7 and all subsequent versions unless a new policy is published._
