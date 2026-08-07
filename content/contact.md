---
title: 'Contact'
date: 2026-08-07
type: landing
sections:
  - block: contact-info
    content:
      title: Contact
      subtitle: Advisory, speaking, and collaboration on governance, public finance, and data.
      connect_title: Get in touch
      text: >-
        I'm most useful on public financial management, state-owned enterprise
        governance, institutional reform, and turning administrative data into
        something decision-makers can actually act on. If your question sits in
        that territory, a short note about what you're working on and what you
        need is the best place to start.
      email: meher.bejaoui@outlook.com
      prospective:
        title: Rather talk it through?
        text: >-
          Book a call if a conversation would get further than an exchange of
          emails. Come with a specific question and we'll make good use of the
          half hour.
        button:
          text: Schedule a 30-minute call
          url: https://calendly.com/meher-bejaoui/30min
    design:
      spacing:
        padding: [0, 0, 0, 0]
  - block: markdown
    content:
      title: Support the work
      text: |
        If something here has been useful, tips are welcome — no pressure either way.

        <div id="kofi-panel-placeholder" style="margin-top:1.25rem;">
          <button type="button" id="kofi-panel-trigger" style="display:inline-flex;align-items:center;gap:0.5rem;border-radius:9999px;padding:0.625rem 1.25rem;font-size:0.875rem;font-weight:500;color:#fff;background-color:#00b9fe;border:none;cursor:pointer;">
            <span aria-hidden="true">☕</span>
            <span>Show tip panel</span>
          </button>
        </div>

        <div id="kofi-panel-mount" style="display:none;margin-top:1.25rem;border-radius:0.75rem;overflow:hidden;max-width:42rem;"></div>

        <script>
        (function () {
          var trigger = document.getElementById('kofi-panel-trigger');
          var placeholder = document.getElementById('kofi-panel-placeholder');
          var mount = document.getElementById('kofi-panel-mount');
          if (!trigger || !placeholder || !mount) return;

          trigger.addEventListener('click', function () {
            var iframe = document.createElement('iframe');
            iframe.src = 'https://ko-fi.com/meherbejaoui/?hidefeed=true&widget=true&embed=true&preview=true';
            iframe.title = 'Support me on Ko-fi';
            iframe.loading = 'lazy';
            iframe.height = '712';
            iframe.referrerPolicy = 'strict-origin-when-cross-origin';
            iframe.setAttribute('sandbox', 'allow-scripts allow-same-origin allow-forms allow-popups allow-popups-to-escape-sandbox');
            iframe.style.cssText = 'border:none;width:100%;padding:0;background:transparent;display:block;';
            mount.appendChild(iframe);
            mount.style.display = 'block';
            placeholder.remove();
          });
        })();
        </script>
    design:
      spacing:
        padding: [0, 0, '3rem', 0]
---
