---
name: write-readme
description: >
  This skill should be used when the user asks to "write a README", "create a README",
  "update the README", "document this project", "document this folder", "add docs for this
  sample", or otherwise writes or rewrites README-style Markdown documentation in a
  repository. It applies the house README style: plain instructional voice, a fixed section
  order, copy-pasteable commands, tables for anything enumerable, and exact specifics.
metadata:
  version: "0.1.0"
---

# Write a README in the house style

Produce READMEs that read like the best sample-repository tutorials: a developer lands on
the page, understands in two sentences what the project does, and can run it by copying
commands top to bottom.

## Workflow

1. **Read the code before writing.** Inspect the directory tree, entry points, dependency
   manifests, deploy/run/cleanup scripts, `.env.example`, and infrastructure files. Every
   command, version, file name, port, and environment variable in the README must come from
   the repository, not from memory. Run `--help` or the commands themselves when it is safe
   and cheap to do so.
2. **Pick the variant** from `references/templates.md`: root/index, tutorial/sample,
   end-to-end use case, integration, or infrastructure-as-code. When unsure, use
   tutorial/sample.
3. **Read `references/style-guide.md`** and apply it in full. It is the source of truth
   for voice, section order, formatting, and wording.
4. **Draft** from the chosen template. Delete any section the project has nothing real to
   say in — never pad a section with filler.
5. **Check an existing README first.** When one exists, keep its accurate facts and
   project-specific terms, and restructure rather than discard. Follow any conventions the
   repository already states (CONTRIBUTING, sibling READMEs) where they conflict with a
   default here.
6. **Self-check** against the checklist at the end of the style guide, then write the file.
7. **Report gaps.** Tell the user anything that could not be verified (an untested command,
   a missing architecture image, an unknown minimum version) instead of inventing it. Leave
   a `<placeholder>` in the file only for values the reader must supply themselves.

## Non-negotiables

- Second person, imperative steps, present tense. No "we will learn".
- One- or two-sentence summary directly under the H1, before any heading.
- Prerequisites before the first command; Clean Up after the last one whenever the project
  creates resources, files outside the repo, or anything that costs money.
- Every command in a fenced block with a language tag; every enumerable set in a table.
- No hype words, no exclamation marks, no badges wall, no decorative emoji.
- Nothing invented: no fictional output, benchmarks, features, or links.
