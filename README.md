# Rently Skills for Claude Code

[Claude Code](https://claude.com/claude-code) skills for the [Rently CLI](https://cdn.rently.com.ar/cli/install.ps1) — manage car rental bookings, customers, fleet, and operations.

## Install

```bash
npx skills add Rentlysoft/rently-skills
```

## Prerequisites

Install the Rently CLI first:

```powershell
# Windows
irm https://cdn.rently.com.ar/cli/install.ps1 | iex

# Linux/macOS
curl -fsSL https://cdn.rently.com.ar/cli/install.sh | bash
```

Then authenticate:

```bash
rently auth login --tenant <TENANT> --client-id <USER> --client-secret <SECRET>
```

## Usage

Once installed, use `/rently` in Claude Code:

```
/rently list today's deliveries for branch office 1
/rently search availability in Miami from April 1 to 5
/rently show me bookings for customer 521
```

Claude will also auto-invoke the skill when it detects Rently-related requests.
