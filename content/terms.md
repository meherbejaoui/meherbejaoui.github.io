---
title: Terms and Privacy Policy
date: 2023-10-24
show_date: false
reading_time: false
---

## Privacy Policy

The privacy of all visitors is important. This page explains what information is collected on this website and how it's used.

## Log Files

Like most websites, this site's hosting provider (GitHub Pages) may log standard technical information about visits, such as IP addresses, browser type, referring/exit pages, and date/time stamps. This information isn't linked to anything personally identifiable. See [GitHub's Privacy Statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement) for details on how GitHub Pages handles this data.

## Cookies and Analytics

This site can use **Google Analytics** to understand which pages people find useful, but **only if you agree to it first**. Until you do, no analytics script is loaded and no analytics cookie is set. If you decline, nothing loads at all — the choice isn't a preference that gets quietly ignored.

If you do agree, Google Analytics sets its own cookies (typically named `_ga` and `_ga_*`) to tell one visitor from another across pages and visits. It runs with IP anonymization enabled, and it records when an outbound link is clicked so I can see which references readers actually follow. No advertising cookies are used, and none of this data is sold or shared for marketing.

If your browser sends a **Global Privacy Control** or **Do Not Track** signal, that's treated as a "no" automatically and you won't be asked at all.

Nothing on this site depends on analytics working, so declining, blocking `googletagmanager.com`, or using [Google's opt-out add-on](https://tools.google.com/dlpage/gaoptout) won't break anything.

<button type="button" id="analytics-choice-reset" hidden class="rounded-md border border-current px-3 py-1.5 text-sm font-medium">Change my choice</button>
<span id="analytics-choice-status" hidden>Your choice has been cleared — reload the page to be asked again.</span>

<script>
  (function () {
    var button = document.getElementById('analytics-choice-reset');
    var status = document.getElementById('analytics-choice-status');
    if (!button || !window.hbConsent) return;
    button.hidden = false;
    button.addEventListener('click', function () {
      window.hbConsent.reset();
      button.hidden = true;
      if (status) status.hidden = false;
    });
  })();
</script>

The only other browser storage used is a small local flag recording that choice, so you aren't asked on every page. It isn't sent anywhere and contains no personal information.

This page is updated whenever what's collected changes.

## License

All original content on this website is released under a [Creative Commons Attribution-ShareAlike 4.0 International](https://creativecommons.org/licenses/by-sa/4.0/) (CC BY-SA 4.0) license unless otherwise noted. You are free to share and adapt, even commercially, as long as you give appropriate credit, provide a link to the license, and indicate if changes were made. If you remix, transform, or build upon the material, you must distribute your contributions under the same license as the original.

***

Your use of this website constitutes acceptance of these terms and policies. This page is reviewed and revised from time to time.
