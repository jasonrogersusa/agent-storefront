# Agent Storefront — prototypes

Vaporware prototypes: turn any retail website into an AI‑ready *Agent Storefront*, then watch a swarm of synthetic shopping agents use it.

## Run

```bash
cd prototypes
python3 -m http.server 8765
# open http://localhost:8765/demo_sim/
```

The simulator embeds the X‑ray prototype in an iframe, so it needs to be served over HTTP (not opened as a `file://`).

## What's here

| Path | What it is |
| :--- | :--- |
| `demo_sim/` | End‑to‑end demo flow: enter a site → audit (Cloudflare agent‑readiness + retail checks) → pin‑pointed issues on the site with a fix basket → Gemini builds a digital twin → agent swarm on the twin → interactive report with QR. |
| `agent_xray_v2/` | **Agent X‑Ray** — a Frankie Shop–style collection page (real product imagery) rendered twice under a draggable seam: the human site vs. the agent's "behind the curtain" view. 18 named agents (Gemini, ChatGPT, Perplexity, Muse, Claude, Copilot, Instinct, a store agent, unverified bots) move as collaborative‑tool cursors executing research‑grounded steps (UCP/ACP handshake, intent search, inventory & fit checks, promo/returns parsing, AP2 mandates, agentic tokens, B2A bundles, abandonment, bot blocks). Supports `?embed=1` (no HUD/controls, streams log via `postMessage`) and `?fixed=1` (agent‑native state). |
| `agent_swarm/` | Earlier swarm‑only prototype (CSS silhouettes, no seam). |
| `agent_xray/` | First X‑ray concept (creamery mock, token‑funnel dissolve). |
| `agent_xray_v2_products.json` | Catalog extracted from the saved Frankie Shop collection page (titles, prices, style numbers, per‑size availability, image filenames). |

All agent behaviour and the audit checks are grounded in the research set (a16z/VGS, Google Cloud + Wayfair + Fiserv, Shopify, Visa, Databricks, Deloitte, Kevel/Scot Wingo, Cloudflare Agent Readiness, ucp.dev, agenticcommerce.dev).

> Product photography and the "The Frankie Shop" name are used as demo material only.
