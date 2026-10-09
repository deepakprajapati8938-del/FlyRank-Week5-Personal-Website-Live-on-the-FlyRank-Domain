# Mobile Fix Log: Deep-Cleaning the Portfolio

I opened my portfolio on a real mobile device and ran an AI accessibility/mobile audit. Here are the specific breaks I found and fixed:

### 1. The Mobile Padding Crush (Layout Break)
- **Before:** The Hero section and Contact section had `padding: 60px` which looked great on desktop, but on mobile, it squished the text into a tiny vertical column.
- **After:** Added a media query for mobile (`max-width: 768px`) reducing the padding to `40px 15px`. The text now spans comfortably across the screen.

### 2. Color Contrast Fail (Accessibility)
- **Before:** The secondary text (paragraphs) was using `#a0a0b0` on a `#0a0a0f` background. While aesthetically pleasing, the contrast ratio was slightly too low for readability outside in the sun.
- **After:** Brightened `--text-secondary` to `#cccccc`. It maintains the sleek dark mode aesthetic but passes WCAG contrast guidelines.

### 3. Untappable Nav Button (Layout)
- **Before:** The `.glass-nav` bar had large left/right padding (`30px`), which caused the "Connect" button to spill out of the screen bounds on very narrow iPhones.
- **After:** Adjusted the mobile nav padding to `10px 15px` and increased the width constraint to `95%` so the button is completely visible and tappable.

### 4. Security on External Links
- **Before:** The social links to GitHub and LinkedIn used `target="_blank"`, which can be a minor security and performance risk.
- **After:** Added `rel="noopener noreferrer"` to all outbound links to ensure they open cleanly without accessing the originating window.

**Final Status:** Checked on real phone. Crisp images, perfectly tappable 50x50px social buttons, and 100% working links!
