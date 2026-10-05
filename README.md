# OSS README Style — a Claude Code plugin

Write and review READMEs in one consistent, tutorial-grade style across all your open source repositories. The style is derived from a study of 741 READMEs in the [Amazon Bedrock AgentCore samples](https://github.com/awslabs/agentcore-samples) repository.

| Information | Details |
|:------------|:--------|
| Type        | Claude Code plugin |
| Components  | 2 skills, 1 style guide, 5 README templates |
| Works with  | Any language, framework, or cloud |
| Complexity  | Beginner |

## Overview

- **`write-readme`** — reads your code, picks a README variant, and writes the file in the house style.
- **`review-readme`** — audits an existing README for accuracy, structure, voice, and formatting, then reports or applies fixes.
- **Style guide** — voice, section order, heading names, tables, callouts, and a self-check list.
- **Templates** — tutorial/sample, step-by-step guide, root or section index, end-to-end use case, and integration/infrastructure-as-code.

## Prerequisites

| Requirement | Install |
|:------------|:--------|
| Claude Code | [Claude Code documentation](https://docs.claude.com/en/docs/claude-code/overview) |

## Quick start

Run these inside Claude Code:

```text
/plugin marketplace add yadv-arvind/oss-readme-style
/plugin install oss-readme-style@oss-readme-style
```

Then ask for a README in any repository:

```text
Write a README for this project
```

## Sample prompts

**Prompt**: "Write a README for this project."
**Expected behavior**: Claude reads the tree, manifests, and scripts, chooses the tutorial/sample template, and writes `README.md` with commands taken from the repository.

**Prompt**: "Review the README in `examples/chat` against our style."
**Expected behavior**: Claude returns a findings table — where, what is wrong, and the fix — with accuracy problems listed first.

**Prompt**: "Make every README in this repo consistent."
**Expected behavior**: Claude reviews each file, reports cross-file differences in heading names and term casing, and applies the fixes.

## How it works

Both skills load automatically when your request matches; you can also run them as `/oss-readme-style:write-readme` and `/oss-readme-style:review-readme`.

1. The skill reads the repository so every command, version, and path comes from your code.
2. It loads the style guide and the matching template.
3. It drafts, runs the self-check, and tells you anything it could not verify.

## Project structure

| File | Description |
|:-----|:------------|
| `.claude-plugin/marketplace.json` | Marketplace entry that makes the repository installable |
| `plugins/oss-readme-style/.claude-plugin/plugin.json` | Plugin manifest |
| `plugins/oss-readme-style/skills/write-readme/SKILL.md` | Writing workflow |
| `plugins/oss-readme-style/skills/write-readme/references/style-guide.md` | The style rules |
| `plugins/oss-readme-style/skills/write-readme/references/templates.md` | README skeletons for the five variants |
| `plugins/oss-readme-style/skills/review-readme/SKILL.md` | Review workflow |

## Configuration

To change the style, edit `style-guide.md` and `templates.md`, raise `version` in `plugin.json`, and push. Update an installed copy with:

```text
/plugin marketplace update oss-readme-style
```

## Clean up

```text
/plugin uninstall oss-readme-style@oss-readme-style
/plugin marketplace remove oss-readme-style
```

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE).
