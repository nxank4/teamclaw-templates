# teamclaw-templates

Community template marketplace for [TeamClaw](https://github.com/nxank4/teamclaw) — pre-built agent teams for content creation, research, coding, and more.

Browse, install, and publish with `teamclaw templates`.

## Available Templates

| Template | Description | Cost/Run | Tags |
|----------|-------------|----------|------|
| [content-creator](templates/content-creator/) | Research, script, SEO, and review pipeline | ~$0.07 | content, youtube, social-media, writing |
| [indie-hacker](templates/indie-hacker/) | Full engineering team for solo devs | ~$0.12 | coding, saas, engineering, startup |
| [research-intelligence](templates/research-intelligence/) | Market research and competitor analysis | ~$0.06 | research, market, analysis, intelligence |
| [business-ops](templates/business-ops/) | Process, validate, and report pipeline | ~$0.05 | business, operations, automation, reporting |
| [full-stack-sprint](templates/full-stack-sprint/) | Full stack feature sprint with QA and docs | ~$0.18 | fullstack, coding, engineering, sprint |

## Usage

```bash
# Browse templates
teamclaw templates list

# Install a template
teamclaw templates install content-creator

# Use a template
teamclaw run --template content-creator "Create YouTube video about AI tools"
```

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for how to create and submit templates.

## Structure

```
templates/
  {template-id}/
    template.json    # Template configuration (validated against template.schema.json)
    README.md        # Documentation
index.json           # Auto-generated template registry
template.schema.json # JSON Schema for validation
```
