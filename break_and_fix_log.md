# Break Your Own Site - Hardening Log

## 1. Speed & SEO Check
- **Speed:** Checked site speed via Lighthouse. The site loads extremely fast due to being pure HTML/CSS without heavy frontend frameworks or JS bundles.
- **Findability/SEO:** 
  - Added `<title>` and `<meta name="description">`.
  - **Fixed:** Added Open Graph (`og:title`, `og:description`, `og:image`, `og:type`) meta tags to ensure social media sharing platforms display a proper preview card instead of a broken generic link.

## 2. "Where It Breaks" Triage

### Fix-Now (Addressed & Fixed)
1. **Broken Navigation Anchor:**
   - **Break:** The "Connect" button in the top navigation bar linked to `href="#connect"`. However, the contact section's ID was `id="contact"`. Clicking the button did nothing.
   - **Fix:** Changed the navigation link to `href="#contact"`.

2. **Missing Social Preview (SEO/Meta):**
   - **Break:** Sharing the site link on messaging apps resulted in an ugly, text-only preview.
   - **Fix:** Added full Open Graph meta tags into the HTML `<head>`.

### Known Limitations (Not fixing right now)
1. **Garbage/Whitespace Form Input:**
   - **Break:** While the HTML5 `required` attribute stops completely empty form submissions, a user can bypass it by typing spaces `"   "` in the Name and Message fields.
   - **Why it's a known limitation:** Native Netlify HTML forms rely entirely on basic browser validation. Hardening this would require writing custom JavaScript to `trim()` inputs before submission, which deviates from the simple native HTML form setup for this phase.

2. **Spam-Clicking the Submit Button:**
   - **Break:** Submitting the form twice rapidly before the page redirects can result in multiple submissions being sent to Netlify.
   - **Why it's a known limitation:** The current form relies on standard browser form submission. Preventing double submissions requires overriding the default behavior with JavaScript (`e.preventDefault()`), disabling the button on click, and sending the data via AJAX `fetch`. We accept this limitation for now to maintain a JS-free form.

3. **Placeholder External Links:**
   - **Break:** Clicking the LinkedIn, Calendly, or Resume (`cv.pdf`) icons leads to broken placeholder URLs.
   - **Why it's a known limitation:** The actual assets (Resume PDF, real Calendly link) are pending completion in upcoming weeks. They are intentionally left as placeholders.
