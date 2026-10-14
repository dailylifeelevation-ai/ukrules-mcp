# UK Rules & Rates (MCP server)

Sourced, date-aware UK tax, payroll and bookkeeping rates and deadlines for AI agents. Every answer comes with the date it applies from
(and to), when it was last checked, and the official GOV.UK (or legislation.gov.uk) page it came from. There is also a UK business check
built on Companies House data.

This repository only describes the hosted service. The service itself is run by Blake's Tec Solutions & Co and is not open source.

**MCP endpoint (Streamable HTTP):** `https://ukrules.dailylifeelevation.workers.dev/mcp`

> Information only, not tax or legal advice. Verify with the source.

## What you can ask

- "What's the UK VAT registration threshold?"
- "What was the VAT registration threshold on 1 January 2023?"
- "When is the next PAYE payment deadline?"
- "What are the National Insurance thresholds for 2026/27?"
- "Check this UK company: <company number>"

Topics include income tax, National Insurance, VAT, corporation tax, capital gains tax, National Minimum Wage, statutory pay, pensions,
student loans and mileage allowances, plus tax and payroll deadlines with the next due date.

## Tools

| Tool | Access | What it does |
|---|---|---|
| `list_topics` | free | Rule topics and how many rules each has |
| `search_rules` | free | Search rule keys, labels and topics |
| `search_uk_company` | free | Up to 10 UK companies matching a name |
| `get_rate` | paid | The value in force for a rule key on a date, with effective dates and source |
| `get_rate_history` | paid | All versions of a rule over time |
| `list_deadlines` | paid | Tax and payroll deadlines with the next due date |
| `check_uk_business` | paid | Companies House facts, filing health, late filing penalty band, officers and PSCs, with source links |

The VAT number check inside `check_uk_business` is **coming soon**.

## Connect

```json
{
  "mcpServers": {
    "ukrules": {
      "type": "http",
      "url": "https://ukrules.dailylifeelevation.workers.dev/mcp"
    }
  }
}
```

With an API key, add `"headers": { "Authorization": "Bearer YOUR_API_KEY" }`.

## Pricing

Free tools need no key or payment. Paid tools work with either:

- **x402 pay-per-call (no account):** $0.005 USDC per call, $0.02 for `check_uk_business`, on Base.
- **API key subscription:** Developer £19/month for 10,000 calls, Pro £49/month for 100,000 calls (`check_uk_business` counts as 2 calls).

Failed calls are not charged. Full details and sign-up: <https://ukrules.dailylifeelevation.workers.dev/pricing>

## Links

- Website: <https://ukrules.dailylifeelevation.workers.dev/>
- Pricing and API keys: <https://ukrules.dailylifeelevation.workers.dev/pricing>
- Terms: <https://ukrules.dailylifeelevation.workers.dev/terms>
- Privacy: <https://ukrules.dailylifeelevation.workers.dev/privacy>
- `llms.txt`: <https://ukrules.dailylifeelevation.workers.dev/llms.txt>
- OpenAPI: <https://ukrules.dailylifeelevation.workers.dev/openapi.json>
- Contact: info@blakestecsolutions.info
