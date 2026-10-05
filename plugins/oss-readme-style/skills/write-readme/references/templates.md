# README templates

Skeletons for the five variants. Replace every `<...>` with facts read from the
repository and delete sections that do not apply. Wording rules are in `style-guide.md`.

## 1. Tutorial / sample (default)

For one runnable example in a folder. Target 100–250 lines.

````markdown
# <Sample name> with <key technology>

<One or two sentences: what it builds, with what, and what makes it distinct.>

| Information | Details |
|:------------|:--------|
| Type        | <Getting started / Feature demo / Advanced example> |
| Language    | <language and version> |
| Framework   | <framework, or "None"> |
| Components  | <services or modules used> |
| Complexity  | <Beginner / Intermediate / Advanced> |

## Overview

<What the sample does, as 3–5 bullets or one short paragraph.>

## Architecture

```
<ASCII flow, or an image reference that exists in the repository>
```

## Prerequisites

| Requirement | Minimum version | Install |
|:------------|:----------------|:--------|
| <tool>      | <version>       | <link or command> |

- <Credential or access requirement, with the exact permissions>

## Quick start

```bash
# 1. Install dependencies
<command>

# 2. Configure
cp .env.example .env
# Edit .env: set <VARIABLE>

# 3. Deploy
<command>

# 4. Run
<command>
```

You should see:

```text
<real, trimmed output>
```

## How it works

1. `<file>` — <what it does>
2. `<file>` — <what it does>

## Sample prompts

**Prompt**: "<input>"
**Expected behavior**: <what happens, naming the tool or code path>

## Project structure

| File | Description |
|:-----|:------------|
| `<file>` | <purpose> |

## Troubleshooting

### Issue: `<literal error text>`
**Solution**: <cause, then fix>

## Clean up

```bash
<command>
```

This deletes <resources>. <Anything that is left behind.>

## Additional resources

- [<Official doc title>](<url>)
````

## 2. Step-by-step guide

For a longer walkthrough. Replace **Quick start** in variant 1 with timed steps,
separated by `---`:

````markdown
## Step 1: <Verb the object> (~<n> min)

<One line of intent.>

```bash
<command>
```

You should see:

```text
<output>
```

### What was generated?

```
<annotated tree with # comments>
```

---

## Step 2: <Verb the object> (~<n> min)
````

End with `## What's next?` — a `Feature | Command | What it does` table — before
**Clean up**.

## 3. Root or section index

For a repository root or a folder of samples. No metadata table.

````markdown
# <Repository or section name>

<One or two sentences: what the collection is and who it is for.>

## Repository structure

| Folder | What's inside |
|:-------|:--------------|
| [`<folder>/`](./<folder>/) | <one line> |

## Finding things

- **<Starting point>** → [`<path>/`](./<path>/)
- **By <dimension>** → `<path>/`, `<path>/`

## Quick start

<The shortest path to something running, as one bash block.>

## Additional resources

- [<title>](<url>)

## Contributing

We welcome contributions. See [CONTRIBUTING.md](CONTRIBUTING.md) for how to report issues
and open pull requests.

## License

This project is licensed under the <license>. See [LICENSE](LICENSE).
````

## 4. End-to-end use case

For a complete application. Up to about 350 lines; move deep material to `docs/`.

- Summary states the business problem and the solution in two sentences.
- Metadata rows: Type, Agent or app type, Components, Vertical, Complexity, SDKs used.
- After **Architecture**, add `## Key features` — bullets in the form
  `**Feature** — concrete behavior`, six at most.
- Add `## Detailed documentation` linking `docs/*.md` when the content exceeds one page.
- Prerequisites as a `Requirement | Description` table, followed by one `> [!IMPORTANT]`
  callout if any prerequisite blocks setup.
- Then Setup, Usage with sample queries, Troubleshooting, Clean up, Additional resources.

## 5. Integration / infrastructure-as-code

For connecting to a third-party tool or deploying with an IaC tool. Keep it compact.

````markdown
# <Project> + <Third-party tool> <purpose>

<Verb-first sentence: "Deploy <thing> with <outcome> sent to [<Tool>](<url>).">

## Architecture

```
<component> → <component>
  └── <what converts or exports>
        └── <destination>
```

## Prerequisites

- <tool and version>
- <third-party account, with what credential is needed>

## Quick start

```bash
# 1. <step>
<command>
```

## What's included

- **<Resource>** — <purpose>

## Files

| File | Description |
|:-----|:------------|
| `<file>` | <purpose> |

## Key configuration

```<language>
<the 5–15 lines that make the integration work>
```

## Clean up

```bash
<command>
```

## Additional resources

- [<Tool documentation>](<url>)
````

For infrastructure-as-code, add `## Customization` (variables as a
`Variable | Default | Description` table) and `## Pricing` (which resources cost money)
before **Clean up**.
