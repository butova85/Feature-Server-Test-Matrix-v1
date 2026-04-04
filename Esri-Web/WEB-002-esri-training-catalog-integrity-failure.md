[BUG] Systemic Navigation Failure: Orphaned "Cartography MOOC" and Legacy Link Decay
ID: WEB-002

Severity: High (Blocker for course access)

Category: Data Integrity / Web Security / UX Consistency

📝 Discovery Path (User Story)
User Dashboard: Noticed the "Cartography MOOC" (attended 2025) appears as bold, non-clickable text in the "My Learning Activity" portal, while other courses remain active.

Global Search: Attempted to locate the course via the Esri Training Catalog. Used the "MOOC" filter; found other inactive courses (e.g., GIS for Climate Action), but Cartography was entirely omitted from results.

External Referral: Located the course via an Esri Blog post ("Cartography. MOOC kicks off April 18"). The provided hyperlink contains a malformed redirect parameter.

🔄 Steps to Reproduce
Navigate to the legacy blog link: https://www.esri.com/training/catalog/596e584bb826875993ba4ebf/cartography./

Observe the 400 Bad Request caused by the trailing dot.

Manually remove the dot to reach the "clean" URL.

Observe the page failing to load and redirecting back to the catalog search.

❌ Actual Result
The page is trapped in a "Legacy Loop." Even with a correct URL, the browser blocks the page due to architectural obsolescence.

🔍 Technical Root Cause Analysis
URL Malformation: The marketing link (John Nelson blog) includes a trailing period inside the rsource parameter, breaking the server-side request.

Search Index Omission: The course has been "Orphaned"—the landing page exists, but the metadata is disconnected from the Training Catalog's searchable database.

Architectural Decay (The Blocker): * The page lacks a <!DOCTYPE html> declaration, triggering Quirks Mode.

Modern browsers (Chrome/Edge 146+) identify the legacy state and trigger Tracking Prevention and CORP (Cross-Origin Resource Policy) blocks.

Console Error: net::ERR_BLOCKED_BY_RESPONSE.NotSameOrigin on dc.js.

Script Failure: Uncaught ReferenceError: s is not defined (Logic crash).

✅ Expected Result
Catalog Integrity: All MOOCs (Active or Archived) should remain searchable in the index to preserve user learning history.

Template Modernization: Update legacy course templates with a valid HTML5 DOCTYPE to prevent security policy blocks in modern browsers.

🖼 Evidence
Source of Malformed Link: Esri Blog (https://www.esri.com/arcgis-blog/products/arcgis-pro/mapping/cartography-mooc-kicks-off-april-18-get-ready-to-live)

Console Logs: Captured 240+ Tracking Prevention blocks and a hard CORP violation.

Dashboard State: Course title rendered as <strong> text rather than an <a> anchor tag.
