# review — rules a proposed taste entry must pass

The rulebook review-kit checks research proposals against
(`review --base main --rules research/REVIEW.md`). It condenses the entry
spec, evidence and formatting rules in `PROTOCOL.md`; when the two
disagree, `PROTOCOL.md` wins and this file is fixed to match.

Reviewers check rules, not taste. Whether a pattern is excellent or spent
is the owner's call. Do not report a finding that amounts to "I disagree
with this trend".

## What is being reviewed

A diff to `plugins/ui-polish/skills/ui-polish/edge.md` and `slop.md`. Each
changed or added numbered entry, or Retirement watch bullet, is one
proposal. The commit message for each proposal carries its evidence and
self-check; read it with `git log` where you can.

## Entry rules

1. **No unbounded interpretable word.** An adjective an implementer has to
   fill in — *slight, subtle, barely visible, quiet, tight, large, low,
   soft, generous, muted* — carries a number or range in the same entry.
   "Low contrast" fails; "`~8–12%` foreground opacity" passes.
2. **Bounded direction, not just magnitude.** If the entry names a hue,
   cast or temperature, it says which way and how far. "A slight warm
   cast" fails; "under ~4 points of RGB spread" passes.
3. **Named fallback for every precondition.** Anything that may be
   unavailable — a webfont, a browser API, real data density — has a
   stated alternative. "Use Tiempos" without a fallback fails.
4. **Standalone.** Readable without a neighbouring entry. "As above",
   "see #12" or an unexplained term defined elsewhere fails.
5. **Falsifiable.** Names a hex, pixel value, duration, weight, CSS
   property, product or year, so a reader can check compliance.
6. **`slop.md` entries state the exception.** Three parts: the pattern in
   bold, what it signals, and a `*Still right:*` case. No exception fails.

## Evidence rule

7. **Named shipped surface.** An added or sharpened entry cites a real
   product, URL and what was observed there, in the entry or its commit
   message. "Widely seen" or "increasingly common" alone fails.
8. **Saturation needs breadth.** A move to Retirement watch or `slop.md`
   cites a screenshot archive (Mobbin, Refero) or many unrelated products,
   not one.

## Format rules

9. **Hard wrap at 79 characters.** No changed line exceeds 79.
10. **Continuous numbering.** Numbered entries count up by one across
    section headings, with no gaps or repeats.
11. **`edge.md` stamp.** Each entry has `*(added YYYY-MM)*` after the bold
    pattern, optionally `*(added YYYY-MM, re-checked YYYY-MM)*`. An
    existing `added` date is never changed.
12. **No duplicate.** An addition does not restate an entry already in
    either file; it should have been proposed as a sharpening instead.
13. **`core.md` is untouched.** Any change to it fails.
