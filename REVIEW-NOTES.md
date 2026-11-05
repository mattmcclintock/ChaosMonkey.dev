# OSS homepage proposal — review notes

Branch: `oss-homepage-proposal` (not deployed; merging to `main` deploys via
GitHub Pages — do not merge until approved).

## What changed

- **Repositioned hero** to the approved messaging: "Connect AI coding
  activity to engineering outcomes." + approved supporting copy +
  "Open source. Self-hosted. Built for engineering teams." kicker.
- **New CTAs**: primary "View on GitHub" → repo; secondary "Get started" →
  `docs/installation.md`. Early-access email form and its AWS Lambda
  endpoint JS removed entirely.
- **"We're open" banner** added below the header.
- **Docker quickstart** code block added to the hero (the two commands from
  the README quickstart).
- **Real product screenshots** replace the previous marketing composites.
  `assets/screens/oss/` now contains four real v0.1.0 captures (AIOI
  dashboard, Productivity-by-tool, Pilot Health, client setup), each
  captioned as synthetic demo data.
- **Sections rewritten**: How it works (Collect → Analyze → Correlate),
  supported-tools row, GitHub delivery-evidence row (optional, honest
  attribution limits), self-hosted/data-ownership cards, managed-instance
  note, contributor note, Community Preview CTA.
- **Claims corrected**: removed causal/ROI-diagnosis language ("traces
  deployment reliability back to AI adoption", "AI Engineering ROI
  Diagnosis" title, "correlation = impact" phrasing), early-access and
  founder-led-onboarding framing, and the "verdict" positioning. Added
  "correlation is not causation", configured-spend-is-an-estimate, and
  identity-only-login notes.
- **SEO/social**: title and meta description updated; `og:` and
  `twitter:card` tags added (uses existing `ChaosMonkey_01@2x.png` — no new
  graphics created).
- **Small fix**: video poster now points at the real file
  `assets/video/demo-poster.png` (the old `assets/videos/` path was a
  1-byte stub, so no poster ever loaded).
- **Footer**: added GitHub/Docs links + independent-project/no-Netflix-
  affiliation note.
- **Naming nod**: hero-irony line → "Different monkeys. Different chaos.
  Yes, we know about the other Chaos Monkey."

## Findings you should know

1. `assets/screens/*.png` (Pipeline-Diagnosis, Performance-Insights,
   Review-and-Merge, Delivery-Outcomes, Tool-Team-Comparison, etc.) are
   designed marketing composites — they do not depict the v0.1.0 UI and
   show metrics (DORA, MTTR, "vs Non-AI" causal deltas) the OSS release
   does not provide. They are unreferenced by the new page but still in
   the repo; recommend deleting them after this proposal is approved,
   unless you want to keep them for other materials.
2. `index-test.html` and `indexA.html` are old alternates still in the
   repo — untouched.
3. The early-access Lambda endpoint no longer receives submissions from
   the homepage. If the hosted-service inquiry flow needs a form, that's a
   separate decision (currently a mailto).
4. The demo video still streams from S3 and YouTube — retained, demoted
   below the real screenshots. It shows the product before the OSS pivot;
   re-record later if it diverges.
5. `og-website` is a stray HTML file; `assets/videos/` is a stub dir.
   Cleanup candidates, untouched.
6. Google Analytics tag retained as-is. Flag if you want it removed for
   the OSS site.
7. `/privacy` and `/terms` were written for the hosted service; they are
   still accurate for the website/hosted business but were not reviewed
   for OSS-specific wording.

## Deployment plan (after approval)

1. Review this branch locally: `python3 -m http.server` in the repo root,
   open `http://localhost:8000`.
2. Merge `oss-homepage-proposal` → `main`. GitHub Pages publishes from
   `main` automatically; `CNAME` keeps `chaosmonkey.dev` mapped.
3. Verify https://chaosmonkey.dev loads, screenshots render, GitHub links
   resolve, and the og:image shows in a social-card validator.
4. Optional follow-ups: delete unused mock screenshots/alternates,
   re-record the demo video on the OSS build.
