# Contributing to TeamClaw Templates

Thanks for contributing to the TeamClaw template marketplace! This guide covers how to create, submit, and get your template accepted.

## Creating a Template

### Quick Start

```bash
teamclaw templates init my-template
```

This scaffolds a new template directory with `template.json` and `README.md`.

### Manual Setup

Create a directory under `templates/` with your template ID (kebab-case):

```
templates/my-template/
  template.json
  README.md
```

### template.json Format

```json
{
  "id": "my-template",
  "name": "My Template Name",
  "version": "1.0.0",
  "author": "your-github-username",
  "description": "What this template does (max 200 chars)",
  "tags": ["tag1", "tag2"],
  "defaultGoalTemplate": "Do {thing} for {project}",
  "estimatedCostPerRun": 0.10,
  "minRuns": 1,
  "agents": [
    {
      "role": "worker-bot",
      "model": "claude-haiku-4-5-20251001",
      "taskTypes": ["research", "analysis"],
      "systemPromptOverride": "You are a specialist in...",
      "compositionRules": {
        "required": true,
        "includeKeywords": ["research", "analyze"]
      }
    }
  ]
}
```

### Required Fields

| Field | Type | Rules |
|-------|------|-------|
| `id` | string | kebab-case, matches directory name |
| `name` | string | Max 60 characters |
| `version` | string | Semantic versioning (e.g., `1.0.0`) |
| `author` | string | Your GitHub username |
| `description` | string | Max 200 characters |
| `tags` | array | Max 5 tags |
| `agents` | array | At least 1 agent |

### Optional Fields

| Field | Type | Description |
|-------|------|-------------|
| `defaultGoalTemplate` | string | Goal template with `{placeholders}` |
| `estimatedCostPerRun` | number | Cost in USD |
| `minRuns` | integer | Recommended minimum runs |
| `requiresWebhook` | boolean | Needs webhook setup |

### Agent Roles

Available roles: `worker-bot`, `tech-lead`, `qa-reviewer`, `rfc-author`

### Agent Fields

| Field | Required | Description |
|-------|----------|-------------|
| `role` | Yes | One of the available roles |
| `model` | No | Claude model ID |
| `systemPromptOverride` | No | Custom system prompt |
| `taskTypes` | No | Task types this agent handles |
| `compositionRules` | No | When to include this agent |

## Submitting a PR

1. Fork this repository
2. Create your template in `templates/your-template-id/`
3. Include both `template.json` and `README.md`
4. Run validation locally: `npx ajv-cli validate -s template.schema.json -d "templates/your-template-id/template.json"`
5. Open a PR to `main`

The CI will automatically validate your template against the schema.

**Do not edit `index.json`** — it is auto-generated after merge.

## Review Criteria

### What gets accepted

- Solves a real workflow that benefits from multi-agent coordination
- Well-written system prompts that give agents clear, focused instructions
- Reasonable agent team size (2-6 agents)
- Accurate cost estimates
- Clear README with example goals and tips

### What gets rejected

- Duplicate of an existing template with no meaningful difference
- Single-agent templates (use TeamClaw directly instead)
- Vague system prompts that don't give agents useful direction
- Missing or incomplete README

## Code of Conduct

- **No malicious prompts** — system prompts must not attempt prompt injection, jailbreaking, or manipulation of other agents
- **No credential harvesting** — templates must not ask users for API keys, passwords, or personal information
- **No harmful content** — templates must not generate spam, misinformation, or content that targets individuals
- **Be constructive** — review feedback should be specific and helpful
