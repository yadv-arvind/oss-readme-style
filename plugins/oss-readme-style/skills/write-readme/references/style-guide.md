# README style guide

The house style for every README in an open source repository. It is derived from a study
of 741 READMEs in a large, multi-author samples repository, keeping the patterns that
served readers and fixing the inconsistencies.

## 1. Reader

- Write for a hands-on developer who wants to run the project today.
- Assume fluency with the platform's basics (shell, git, the language toolchain, the cloud
  provider's CLI and permissions model). Do not explain them.
- Define project- or domain-specific concepts once, in one line, at first use.
- State the difficulty (Beginner / Intermediate / Advanced) and, for step-by-step guides,
  a time estimate per step: `## Step 1: Create the project (~1 min)`.

## 2. Voice

- **Person:** second person ("you", "your"). Never "we will learn"; avoid "we" except for
  maintainers speaking as a project ("We welcome contributions").
- **Mood:** imperative for steps — "Deploy the stack", "Verify your credentials", "Note
  the `RepositoryUri` from the output".
- **Tense:** present. "The script creates a role", not "will create".
- **Register:** plain and declarative. Contractions are fine. No exclamation marks.
- **Sentence length:** aim for about 17 words; split anything over 30.
- **Banned hype:** seamless, powerful, robust, cutting-edge, revolutionary, leverage,
  comprehensive, enterprise-grade, simply, just, easy. Use "production-ready" only when the
  project genuinely is, and say what makes it so.
- **Honesty:** explain why a thing behaves as it does and name the gotcha. Prefer "A
  `CREATING` status past the one-minute mark is normal, not a failure" to reassurance.
- **Politeness:** no "please" in steps.

## 3. Opening

- **H1:** the project or sample name, in the form `X with Y` or `X — Y`. No emoji, no
  badge wall. At most one row of badges on a repository root README.
- **Summary:** one or two sentences immediately under the H1, before any heading. Choose
  one opener:
  - Verb-first: "Deploy a travel agent to the runtime with traces sent to Arize."
  - Noun phrase: "A bidirectional voice agent supporting three speech-to-speech models."
  - Demonstrative: "This sample demonstrates two outbound OAuth2 flows in a single agent."
- The summary names what is built, with what, and the one thing that makes it distinct.
- Do not open with industry context ("As organizations adopt..."). If background is
  needed, put two or three sentences in Overview.

## 4. Section order

Use this order. Omit a section rather than fill it with nothing.

| # | Section | Contents |
|---|---------|----------|
| 1 | H1 + summary | See Opening |
| 2 | Metadata table | `Information / Details` — tutorials, samples, and use cases only |
| 3 | `## Overview` or `## What you'll build` | What it does, as 3–5 bullets or one short paragraph |
| 4 | `## Architecture` | One diagram, then a component table or a few bullets |
| 5 | `## Prerequisites` | Tools with minimum versions, credentials, access, permissions |
| 6 | `## Quick start` or numbered `## Step N:` sections | Runnable top to bottom |
| 7 | `## How it works` / `## Key concepts` | Mechanism; bold term lead-ins |
| 8 | `## Sample prompts` / `## Usage` | Inputs to try, with expected behavior |
| 9 | `## Configuration` | Environment variables and options, as a table |
| 10 | `## Project structure` | Annotated tree or a file table |
| 11 | `## Troubleshooting` | Issue / Solution pairs |
| 12 | `## Clean up` | Commands, and what they delete |
| 13 | `## Next steps` | Arrows to sibling samples or deeper docs |
| 14 | `## Additional resources` | Link list |
| 15 | `## Contributing`, `## License` | Repository root README only |

Length: 100–350 lines for a sample. Move anything longer into `docs/` and link to it.
Add a table of contents only above roughly 300 lines.

## 5. Headings

- Sentence case: `## Clean up`, `## How it works`, `## Sample prompts`.
- Use these exact names so READMEs match across repositories: Overview, Architecture,
  Prerequisites, Quick start, How it works, Key concepts, Sample prompts, Usage,
  Configuration, Project structure, Troubleshooting, Clean up, Next steps, Additional
  resources.
- Steps: `## Step 1: Create the project (~1 min)` or `### 1. Install dependencies`.
- A question heading is allowed for an explainer directly after code: `### What's
  happening here?`, `### What was generated?`
- No emoji in headings. No skipped levels.

## 6. Metadata table

Directly under the summary for tutorials, samples, and use cases:

```markdown
| Information    | Details                                   |
|:---------------|:------------------------------------------|
| Type           | Getting started                           |
| Language       | Python 3.12                               |
| Framework      | Strands Agents                            |
| Model          | Claude Sonnet 4.6                         |
| Components     | Runtime, Memory, Gateway                  |
| Complexity     | Beginner                                  |
```

Keep the row names identical across a repository. Complexity is exactly one of Beginner,
Intermediate, Advanced. Drop rows that do not apply.

## 7. Architecture

- One diagram near the top: an image (`![Architecture](images/architecture.png)`) or an
  ASCII box-and-arrow diagram in an untagged fence. Use ASCII when no image exists — do
  not reference an image that is not in the repository.
- Follow it with a `Component | Purpose` table or 3–5 bullets naming each part.
- For a request flow, one line with arrows is enough:
  `deploy.py → zip + upload → create runtime → status: READY`.

## 8. Prerequisites

- A table for tools: `Requirement | Minimum version | Install`.
- Then credentials and access, each with the command that verifies it:

  ```bash
  aws sts get-caller-identity
  ```
- Name exact permissions, policies, or scopes. Never "appropriate permissions".
- State cost-bearing or account-level requirements here (model access, quotas, paid
  accounts, API keys).

## 9. Steps and commands

- One line of intent, then the command block, then what to expect.
- Every command is copy-pasteable: no shell prompt (`$`), a language tag on every fence
  (`bash`, `python`, `json`, `text` for output).
- Chain related commands in one block with `#` comments above each.
- Pin versions that matter: `npm install -g some-cli@0.30.0`.
- Reader-supplied values use angle brackets, lowercase with hyphens: `<your-api-key>`.
  Environment variables use `UPPER_SNAKE_CASE`.
- Show expected output after commands whose success is not obvious. Introduce it with
  "You should see:" and use real output, trimmed.
- After a large pasted code block, add `### What's happening here?` with one paragraph
  explaining the two or three lines that matter.
- State the default region, port, or profile once, and how to change it.

## 10. Lists and tables

- Tables for anything enumerable: files, components, endpoints, options, commands,
  environment variables, comparisons. Left-align columns (`|:---|`).
- Definition-style bullets use a bold lead-in and an em dash:
  `- **Session ID** — a UUID that identifies one isolated VM.`
- Use numbered lists only for sequence, bullets for sets.
- Navigation and flows use arrows:
  `- **By protocol** → [`01-http/`](./01-http/)`.

## 11. Sample prompts and usage

```markdown
**Prompt**: "What files are in the current directory?"
**Expected behavior**: The agent runs `ls -la` with the `shell` tool and reports the contents.
```

Give 3–4 inputs that exercise different paths, including one multi-step case.

## 12. Callouts

- GitHub alerts, used sparingly: `> [!NOTE]`, `> [!TIP]`, `> [!IMPORTANT]`,
  `> [!WARNING]`. At most one per section.
- IMPORTANT is for something that breaks the walkthrough if skipped; WARNING for data
  loss, cost, or security.
- Emoji only as status marks inside tables or checklists (✅ ⚠️). None elsewhere.

## 13. Troubleshooting

```markdown
### Issue: `AccessDeniedException` when creating the role
**Solution**: Your credentials lack `iam:CreateRole` and `iam:PutRolePolicy`. Attach them
to your user or role, then rerun `deploy.py`.
```

Quote the literal error text in the heading. Give the cause, then the fix. Include only
problems that were actually hit or are likely from the code.

## 14. Clean up

- Required whenever the project creates anything outside the working directory.
- Give the command, then one sentence listing what it deletes.
- Mention anything that survives (log groups, shared roles, buckets with data).

## 15. Links and closing

- Link the first mention of an external product, library, or standard to its official
  documentation. Link siblings with relative paths.
- Never fabricate a URL. Check that relative links resolve.
- End with `## Additional resources` as a bullet list of 3–6 links. On a root README, end
  with Contributing and License, each one or two sentences pointing to the file.
- A not-for-production disclaimer, when the code is a demo, is one sentence under a
  `## Disclaimer` heading at the very end.

## 16. Terms and mechanics

- Use the official casing of every product, library, and protocol name, and keep it
  identical throughout the repository. Spell a name in full at first mention, then use the
  short form.
- Inline code for commands, file names, paths, parameters, values, and status strings.
- Bold for UI labels and for a term being defined. No italics for emphasis.
- Wrap prose at natural sentence boundaries; do not hard-wrap mid-sentence in new files.
- Spell out an acronym at first use unless the audience uses it daily (API, CLI, SDK).

## 17. Self-check

- [ ] A newcomer learns what this is from the first two sentences.
- [ ] Every command was read from the repository or run, and is in a tagged fence.
- [ ] Prerequisites list versions and exact permissions, each verifiable.
- [ ] Steps run top to bottom with no hidden step between them.
- [ ] Enumerable content is in tables.
- [ ] Clean up exists and says what is removed.
- [ ] No hype words, exclamation marks, decorative emoji, or "we will".
- [ ] Heading names and term casing match the rest of the repository.
- [ ] All links and image paths resolve; nothing is invented.
