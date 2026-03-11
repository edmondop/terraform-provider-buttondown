# Buttondown IaC Providers

Terraform and Pulumi providers for [Buttondown](https://buttondown.com) — manage your newsletter as code.

## Why

Stop clicking through dashboards. Version-control your newsletter configuration, email drafts, automation rules, and more. Review changes in PRs. Roll back mistakes with `git revert`.

## Terraform Provider

### Quick Start

```hcl
terraform {
  required_providers {
    buttondown = {
      source  = "edmondop/buttondown"
      version = "~> 0.1"
    }
  }
}

provider "buttondown" {
  # Set via BUTTONDOWN_API_KEY env var or here
}

resource "buttondown_email" "weekly_update" {
  subject = "Weekly Update"
  body    = file("emails/weekly-update.md")
}
```

### Resources

| Resource | Description |
|----------|-------------|
| `buttondown_email` | Email drafts (created as draft, never auto-sent) |
| `buttondown_automation` | Automation rules |
| `buttondown_tag` | Tags for organizing content |
| `buttondown_webhook` | Webhook subscriptions |
| `buttondown_snippet` | Reusable content blocks |
| `buttondown_form` | Subscription forms |
| `buttondown_external_feed` | RSS/Atom feed imports |
| `buttondown_survey` | Reader surveys |
| `buttondown_book` | Reading list items |
| `buttondown_user` | Team members |
| `buttondown_newsletter` | Newsletter configuration |

### Data Sources

| Data Source | Description |
|-------------|-------------|
| `buttondown_account` | Current account info |

## Development

```bash
# Install tools
mise install

# Build
mise run build

# Test
mise run test

# Acceptance tests (requires BUTTONDOWN_API_KEY)
mise run testacc

# Lint
mise run lint
```

## License

MIT
