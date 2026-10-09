# "Survive the Crit" - Design Review Feedback

As part of the Week 6 "Survive the Crit" assignment, I asked a peer to review my live portfolio. Here is the feedback collected, sorted without defense, and my fix log.

## 1. Initial 10-Second Impressions
- **In ten seconds, what do I do?** 
  "You're a Backend Engineer and AI Agent Developer who builds robust data pipelines and autonomous agents." (Clearly visible in the hero text).
- **Would I believe you're good at it?** 
  "Yes. The dark-mode glassmorphism aesthetic feels very modern and technical. The two highlighted projects (Tech Research Agent and Polite Scraper) show you build serious backend logic and don't just rely on frontend UI to look impressive."

## 2. Feedback Sorting & Action Plan

### Must-Fixes (Confusing, broken, or hurts the main action)
1. **The "Open to Opportunities" badge is static.** It looks like a button but nothing happens when you click it. It should drive action (like scrolling to the contact form) so recruiters can immediately reach out.
2. **The Capstone Placeholder text.** Leaving `[ FlyRank Completion Badge Will Appear Here ]` in brackets looks like broken, forgotten developer code to a recruiter who doesn't know the FlyRank program context. It needs to look intentional.

### Nice-to-Have (Later)
1. **Smooth Scrolling.** When clicking "Projects" or "About" in the nav, it jumps abruptly. A smooth scroll animation would make it feel much more premium.

## 3. Fix Log (What I Changed)
I accepted the feedback without defending the original design and implemented the following changes on the live site:

- **Fixed Must-Fix #1:** Changed the `<div class="status-badge">` to an `<a>` tag linking to `#contact`. Now, if a recruiter clicks "Open to Opportunities", they are smoothly scrolled directly to the contact form.
- **Fixed Must-Fix #2:** Replaced the bracketed placeholder text with stylized, italicized text: *Reserved for Official FlyRank Completion Badge*. Now it looks like a deliberate "coming soon" tease rather than missing code.
- **Bonus (Fixed Nice-to-Have):** Added `scroll-behavior: smooth;` to the CSS `html` tag. Now all navigation links gracefully glide down the page instead of snapping instantly.
