# Campaign Brief → Funnel-Ready Asset Kit

One campaign brief in. A full funnel out.

Enter a product, audience, objective, and budget tier once, and get back:

- **Paid ad variants** for Meta, TikTok, and Google copy that respects
  each platform's real constraints (Google Search headlines ≤ 30
  characters, descriptions ≤ 90, etc.)
- **Organic captions** for Instagram, TikTok, and Facebook
- **UTM-tagged links**, auto-built from your destination URL
- **The KPIs worth watching**, tailored to funnel stage; awareness,
  consideration, and conversion each track different things, and this
  tool doesn't hand you the same five metrics for all three

Everything is organized by funnel stage first, platform second because
that's how a campaign actually gets planned, not how most ad copy
generators structure their output.

Free to run, free to fork, no data stored.

## Three ways to use this

| Version | Where it runs | Setup |
|---|---|---|
| **Claude artifact** | Directly inside claude.ai | None, open the `.html` file as an artifact and go |
| **Replit app** | Your own public URL | `replit-app/`, add one API key, click Run |
| **Relay.app workflow** | No-code automation, Slack/Sheets output | `docs/RELAY_SETUP.md`, paste a spec into Relay's builder |

### Claude artifact

`claude-artifact.html` is self-contained and calls the Claude API through
claude.ai's built-in proxy, no API key needed on your end. Paste it into
a new artifact in claude.ai, or run it in any environment where Claude can
create artifacts that call its own API.

### Replit app

1. Import this repo into a new Replit Python project (or upload the
   `replit-app/` folder).
2. In Replit's **Secrets** tab, add `ANTHROPIC_API_KEY` with your own key.
3. Click **Run**. Replit installs `requirements.txt` automatically.
4. Share the public URL Replit gives you, that's a live, free tool
   anyone can use.

The API key stays server-side (`app.py` holds it, not the browser), so
it's safe to make the Repl public.

### Relay.app workflow

See `docs/RELAY_SETUP.md`. Relay builds workflows from a natural-language
description rather than an importable file, so that doc is a script you
paste into Relay's builder, it scaffolds the steps, including a
human-approval gate before anything gets written to your Sheet or posted
to Slack.

## How it thinks about funnel stages

| Stage | Ad tone | What to track |
|---|---|---|
| **Awareness** | Curiosity, attention-grabbing hook | Reach, CPM, video view rate |
| **Consideration** | Value, proof, a reason to trust you | CTR, engagement rate, landing page views |
| **Conversion** | Urgency, offer, a clear next step | CVR, CPA, ROAS |

The prompt behind this tool encodes that logic directly, so the same
product brief produces genuinely different copy at each stage, not the
same ad reworded three times.

## Project structure

```
funnel-asset-kit/
├── claude-artifact.html      # Standalone Claude-artifact version
├── replit-app/
│   ├── app.py                 # Flask backend (holds the API key)
│   ├── templates/index.html   # Form UI
│   ├── static/style.css
│   ├── static/app.js
│   ├── requirements.txt
│   ├── .env.example
│   └── .replit                # Replit run config
├── docs/
│   └── RELAY_SETUP.md         # Relay.app workflow spec
├── LICENSE
└── README.md
```

## Contributing

Forks and pull requests welcome, adding platforms (Pinterest, LinkedIn
Ads), localized copy, or a CSV export of the generated kit would all be
natural next steps.

## License

MIT — see `LICENSE`. Use it, fork it, put your own name on the deploy.
