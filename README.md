# Sponsor Finder

A free plugin from [SPath Global](https://spathglobal.com) that lets you search and check employers on the UK Home Office register of licensed visa sponsors, right inside your AI assistant.

Ask things like:

- "Can Deloitte sponsor a Skilled Worker visa?"
- "Find software companies in Manchester that are licensed sponsors."
- "Which NHS trusts in Leeds can sponsor visas?"

## What's included

| Part | What it does |
|---|---|
| `check_sponsor` tool | Checks whether a named employer is on the register and shows its licensed routes and rating. |
| `search_sponsors` tool | Searches the register by company name or keyword, with optional town or city and visa route filters. Returns up to 25 organisations. |
| `find-sponsors` skill | Tells the assistant when to use each tool and how to explain the results honestly. |

## Install in Claude Code

```bash
claude plugin marketplace add richardogundele/sponsor-finder
claude plugin install sponsor-finder@spath-sponsor-finder
```

## How it works and what it sends

This plugin connects to one read-only service run by SPath Global:

`https://mdkorcgraconorwiflzf.supabase.co/functions/v1/sponsor-search-mcp`

When the assistant uses a tool, it sends only the search words you asked about (a company name, keyword, town or visa route). The service looks them up in SPath Global's copy of the public UK register of licensed sponsors and returns matching organisations. It needs no login and never asks for your CV or personal details. SPath Global does not save your searches. Our hosting provider (Supabase) keeps standard request logs, which can include your IP address and the time of the request, for security and troubleshooting.

The register data comes from the UK Home Office's published list of licensed sponsors and may be a few weeks behind the latest version on GOV.UK.

Privacy policy: https://spathglobal.com/privacy
Terms: https://spathglobal.com/terms

## Important

A sponsor licence means an organisation **can** sponsor visas. It is not evidence of a current vacancy, and it does not mean the employer will sponsor a particular role. Always confirm with the employer and check the specific job before applying. This plugin does not give immigration or legal advice.

## Support

https://spathglobal.com/plugin-support

## More from SPath Global

- [Sponsorship CV](https://github.com/richardogundele/sponsorship-cv): a free plugin that tailors your CV and cover letter to a job.
- [Find UK sponsors on the web](https://spathglobal.com/finduksponsors)

## Licence

MIT. See [LICENSE](LICENSE).
