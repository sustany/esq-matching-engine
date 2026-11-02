# ESQ Matching Engine

Find, compare and contact licensed U.S. lawyers from Claude.

ESQ Matching Engine matches people with licensed attorneys by relevance; the user chooses whom to contact. License and office details come from official state licensing records. Practice areas are what lawyers listed themselves. Fees and availability appear only where a lawyer has shared them; everything else is labeled unknown. ESQ Matching Engine does not give legal advice, does not rank lawyers by payment, and a match or introduction does not create an attorney-client relationship.

## What it does
- **get_matching_requirements**: the questions needed for a good match
- **find_attorneys**: up to five licensed lawyers with reasons, sources and dates, or an honest no-match with legal aid links
- **compare_attorneys**, **get_attorney_profile**: side-by-side facts and one lawyer's profile
- **estimate_legal_cost**: fee information only where it has a real source; otherwise it says so
- **check_attorney_availability**: availability a lawyer has reported; no calendar is connected
- **request_attorney_introduction**, **get_referral_status**: an introduction to one lawyer, only after the user agrees to exactly what is shared
- **update_matching_preferences**, **submit_matching_feedback**

## Install

**Claude Code** (version 2.1.275 or later), one step:

```
/plugin install esq-matching-engine --marketplace sustany/esq-matching-engine
```

Older Claude Code versions, two steps:

```
/plugin marketplace add sustany/esq-matching-engine
/plugin install esq-matching-engine@esq-copilot
```

**Claude on the web, desktop or mobile:** Settings, Connectors, Add custom connector. Name: ESQ Matching Engine. Remote MCP server URL: `https://match.esqcopilot.com/mcp`. No sign-in.

The plugin adds the remote MCP server `https://match.esqcopilot.com/mcp` (no sign-in) and a short skill (`find-a-lawyer`) that tells Claude how to use it.

## Introductions today
`request_attorney_introduction` records the request and the details the person approved, and returns a reference number. While introduction delivery is switched off, the request is recorded only and is not sent to the lawyer; the tool says so in its answer, and Claude must tell the person.

## Examples
- "My landlord gave me a 3-day notice in Santa Ana, California. Find me a lawyer; my budget is small."
- "Compare the first three lawyers you found."
- "What would a landlord-tenant lawyer in California cost?"
- "I was fired after complaining about unpaid overtime in Los Angeles. Who can help?"
- "Introduce me to the second lawyer." (Claude shows the lawyer and the exact details first, and sends nothing without your yes.)

## What this plugin sends and runs
Nothing runs on your computer. The plugin connects Claude to one remote server, `https://match.esqcopilot.com/mcp`, operated by Decentralized Publishing LLC. Claude sends it the search details needed for a match (state, city or county, type of matter, timing, budget, language). For an introduction, it sends only the details you approve. It never reads your chat history, files or memory.

## Privacy and terms
Privacy policy: https://esqcopilot.com/privacy.html. Terms: https://esqcopilot.com/terms.html. Searches keep structured criteria only, never the person's own description. Introduction details are limited to what the person approves, encrypted, and deleted after 180 days.

## Support
https://esqcopilot.com/contact.html, notices@esqcopilot.com. Operated by Decentralized Publishing LLC, 92 Corporate Park, Ste C #1083, Irvine, CA 92606.
