# Website redesign audit checklist (embeddable form)

The fillable form for the guide
[20 questions to ask before a website redesign](https://tillerdigital.com/guides/website-audit-checklist-20-questions-to-ask-before-a-website-redesign/):
20 questions with a Yes / Partial / No / Unsure dropdown and notes, PDF and XLSX downloads of the answers, and the Book a Call CTA.
It has no header or footer and a transparent background, so it sits inside an existing page's content container.

## Embed

```html
<iframe id="tiller-audit-checklist"
  src="https://thronesgit.github.io/website-audit-checklist/"
  title="Website redesign audit checklist"
  style="display:block;width:calc(100% + 8px);margin:0 -4px;height:3000px;border:0"
  loading="lazy"></iframe>
<script>
  window.addEventListener('message', function (e) {
    if (e.origin !== 'https://thronesgit.github.io') return;
    if (e.data && e.data.type === 'tiller-audit-height') {
      document.getElementById('tiller-audit-checklist').style.height = e.data.height + 'px';
    }
  });
</script>
```

- The form reports its height to the parent page, so the iframe grows to fit and never scrolls on its own.
- The -4px margin lines the form up with the column edge (the form keeps 4px of room for focus outlines).
- If the iframe is sandboxed, allow `allow-scripts allow-same-origin allow-downloads allow-popups allow-top-navigation-by-user-activation`.
- Served from tillerdigital.com (for example as a file in the theme), the form picks up the site's own fonts; change the `src` and the origin check to match.
- Answers stay in the visitor's browser. Nothing is sent anywhere.
