---
name: review-readme
description: >
  This skill should be used when the user asks to "review the README", "check the README
  style", "audit the docs", "make this README consistent", "does this README follow our
  style", or wants existing README-style Markdown compared against the house README style
  and corrected.
metadata:
  version: "0.1.0"
---

# Review a README against the house style

1. Read the target README and enough of the repository to verify its claims (tree, entry
   points, manifests, scripts).
2. Read `../write-readme/references/style-guide.md` — the source of truth — and the
   matching variant in `../write-readme/references/templates.md`.
3. Check, in this order:
   - **Accuracy** — commands, paths, versions, environment variables, and links match the
     repository. Broken or stale instructions outrank every style finding.
   - **Structure** — summary under the H1, section order, missing Prerequisites, missing
     Clean Up, steps that are not runnable top to bottom.
   - **Voice and wording** — person, tense, hype words, sentence length, term casing.
   - **Formatting** — code-fence language tags, tables, callouts, placeholders, heading
     case, emoji.
4. Report findings as a table, most serious first:

   | # | Where | Finding | Fix |
   |---|-------|---------|-----|

   Quote the offending text briefly and give the concrete replacement. Do not list things
   that are already correct.
5. Apply the fixes when the user asked for a fix or a rewrite; otherwise stop after the
   report and offer to apply them. When several READMEs are in scope, also report
   cross-file inconsistencies (differing heading names, term casing, section order).
