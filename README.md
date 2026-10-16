# Agent Storefront — prototypes

Vaporware prototypes exploring agentic commerce for retail. Two demo flows share one visual engine.

**Live:** https://jasonrogersusa.github.io/agent-storefront/

## Run locally

```bash
cd prototypes
python3 -m http.server 8765
# open http://localhost:8765/
```

The demos embed the X‑ray engine in an iframe, so they need to be served over HTTP (not opened as `file://`).

## Folder map

```
prototypes/
├── index.html              landing page linking both demos
├── open-for-agents/        DEMO 1 · site readiness
│   └── index.html          enter site → audit → pinned fixes + basket → build twin → swarm → report
├── demand-signals/         DEMO 2 · demand listening
│   └── index.html          generate shopping agents → swarm → demand map → product + try‑on
├── shared/
│   └── agent_xray_v2/      THE ENGINE · Agent X‑Ray (used by both demos via iframe)
│       ├── index.html      human site vs. agent view under a draggable seam; 18 scripted agents
│       ├── img/            real product photography (8 SKUs)
│       └── products.json   catalog extracted from the saved Frankie Shop collection page
└── archive/                early concepts, kept for reference
    ├── agent_xray/         first X‑ray (creamery mock, token‑funnel dissolve)
    └── agent_swarm/        first swarm (CSS silhouettes, no seam)
```

## The engine: `shared/agent_xray_v2`

A Frankie Shop–style collection page rendered twice under a draggable seam — the human site on the left, the agent's "behind the curtain" view on the right (parsed data cards, unreadable promo, policy‑from‑prose, protocol 404s). Eighteen named agents (Gemini, ChatGPT, Perplexity, Muse, Claude, Copilot, Instinct, a store agent, unverified bots) move as collaborative‑tool cursors executing research‑grounded steps: UCP/ACP handshake, intent search, inventory & fit checks, promo/returns parsing, AP2 mandates, agentic tokens, B2A bundles, abandonment, bot blocks.

Query params when embedding:

| Param | Effect |
| :--- | :--- |
| `?embed=1` | hides HUD/controls, streams `{type:'log'}` and `{type:'tally'}` via `postMessage` to the parent |
| `?fixed=1` | starts in the agent‑native (fixed) state |

Parent can send `'fix'`, `'pause'`, `'play'` via `postMessage`.

## Grounding

Agent behaviour and audit checks come from the research set: a16z/VGS, Google Cloud + Wayfair + Fiserv (UCP/AP2), Shopify, Visa Intelligent Commerce, Databricks, Deloitte, Kevel/Scot Wingo, Cloudflare Agent Readiness (`isitagentready.com`), ucp.dev, agenticcommerce.dev.

> Product photography and the "The Frankie Shop" name are used as demo material only.
