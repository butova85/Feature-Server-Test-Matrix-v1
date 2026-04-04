# [BUG] Missing Favicon Metadata on Job Position Templates
**Severity:** Low (UI/UX Branding Inconsistency)  

## 💻 Environment
* **Microsoft Edge:** Version 146.0.3856.72 (Official build) (64-bit)
* **Google Chrome:** Version 146.0.7680.165 (Official build) (64-bit)

## 📝 Summary
Individual job position pages (e.g., Data Scientist I) fail to display the corporate favicon in the browser tab. This appears to be a regression or omission in the specific page template used for job descriptions.

## 🔄 Steps to Reproduce
1. Start at the main Esri-hosted Careers page: `https://www.esri.com/en-us/about/careers/job-search`
   * **Observation:** Favicon is **Present**.
2. Click on a job or navigate to the direct position URL: `https://www.esri.com/careers/4953727007?title=data-scientist-i`
   * **Observation:** Favicon is **Missing**.

## 🔍 Technical Analysis (Root Cause)
* **Directory Discrepancy:** The main search page is hosted under the `/en-us/about/careers/` subdirectory, while the position detail pages are served from `/careers/`.
* **Template Audit:** The `/careers/` template has not been configured with the `<link rel="icon">` metadata found in the main corporate site headers.
* **DevTools Verification:**
    * Main Page: 4 favicon-related tags found in Elements`.
    * Position Page: 0 favicon-related tags found in `Elements`.

## ✅ Expected Result
The `/careers/` position template should be updated to include the corporate favicon assets to ensure a seamless transition for applicants moving from the search page to the application page.

## 🖼 Evidence
*Screenshot:(../Assets/missing-favicon.png)
