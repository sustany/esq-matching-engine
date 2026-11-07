# ESQ Matching Engine

Search, compare and contact licensed U.S. lawyers from Claude.

ESQ Matching Engine is a listing service, not a lawyer referral service. No lawyer pays for placement or ranking of any kind, and the person chooses whom to contact. License and office details come from official state licensing records. Practice areas are what lawyers listed themselves. Fees and availability appear only where a lawyer has shared them; everything else is labeled unknown. ESQ Matching Engine does not give legal advice, and a listing or a message does not create an attorney-client relationship.

## What it does
- **get_search_filters**: the few filters still needed before a search
- **search_attorneys**: licensed lawyers that fit the person's filters, in the order the person picks (nearest office by default; also last name, years licensed, free first consultation, published fees or reported availability), with no scores. Each answer starts with a plain summary, gives shared notes once and each lawyer's own facts with sources and dates, and pages through the full list; or an honest empty result with legal aid links
- **start_from_directory_profile**: start from one directory profile and keep that lawyer visible
- **compare_attorneys**, **get_attorney_profile**: side-by-side facts and one lawyer's profile
- **estimate_legal_cost**: fee information only where it has a real source; otherwise it says so
- **check_attorney_availability**: availability a lawyer has reported; no calendar is connected
- **preview_client_message**, **send_client_message**, **get_contact_request_status**, **cancel_contact_request**: the person's own message to one lawyer they picked, only after they approve its exact text (optional; the firm's phone and website are always shown too)
- **prepare_case_brief**: puts the person's own notes in order before they call a lawyer: their words kept unchanged, a dated timeline, papers to bring and questions to ask, each item labeled as the person's statement or a suggestion. Deadlines are shown exactly as the person reported them and are not checked. Stores nothing and sends nothing
- **get_matter_tracker**: where each message the person sent stands (up to 10), with a dated timeline and the real status from its record. Failed and cancelled messages are shown too. A consultation counts only when confirmed
- **update_listing_criteria**, **submit_listing_feedback**, **report_listing_error** (report a wrong or outdated detail; it never changes the order)
- Older tool names (find_attorneys, request_attorney_introduction and others) keep working until 2026-12-15.
## What's new in 4.0.0
- Organize my case notes (`prepare_case_brief`) and Track my messages (`get_matter_tracker`) are now part of the skill.
- Plain requests such as "who can represent me?" or "I need someone to defend me" start a search.

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

## Messages today
`send_client_message` passes along only the message and details the person approved, to the email on the lawyer's licensing record, and returns a reference number. The lawyer replies to the person directly. If sending is switched off, the message is recorded only; the tool says which in its answer, and Claude must tell the person.

## Examples
- "My landlord gave me a 3-day notice in Santa Ana, California. Show me licensed tenant lawyers there; my budget is small."
- "Compare the first three listings."
- "What would a landlord-tenant lawyer in California cost?"
- "I was fired after complaining about unpaid overtime in Los Angeles. Who can help?"
- "Help me organize my notes about unpaid overtime before I call a lawyer."
- "I got a DUI in Columbus, Ohio last night. Who can represent me?"
- "What happened with the message I sent to the lawyer earlier?"
- "Send my message to the second lawyer." (Claude shows the lawyer and the exact text first, and sends nothing without your yes.)

## What this plugin sends and runs
Nothing runs on your computer. The plugin connects Claude to one remote server, `https://match.esqcopilot.com/mcp`, operated by Decentralized Publishing LLC. Claude sends it the search filters (state, city or county, type of matter, timing, budget, language). For organizing notes, it sends only what you wrote, and nothing is stored. For a message, it sends only the details you approve. It never reads your chat history, files or memory.

## Privacy and terms
Privacy policy: https://esqcopilot.com/privacy.html. Terms: https://esqcopilot.com/terms.html. Searches keep structured criteria only, never the person's own description. Message details are limited to what the person approves, encrypted, and deleted after 180 days.

## Support
https://esqcopilot.com/contact.html, notices@esqcopilot.com. Operated by Decentralized Publishing LLC, 92 Corporate Park, Ste C #1083, Irvine, CA 92606.
