# Popup Node

A web app for an NFC popup. Each person writes three sentences: what they are looking for (SEEK), what they can offer (OFFER), and what they want to imagine together (IMAGINE). Only the overlaps show up as lines in a constellation.

Live site: [node.cyp3.xyz](https://node.cyp3.xyz).

## Run locally

```bash
npm install
npm run dev
```

Open http://localhost:3000

It starts without environment variables. Local data is written to `data/store.json`, and that file is not committed.

## Environment variables

No secret values are in this repo. The names are listed in `.env.example`. Put real values in `.env.local`.

| Name | When unset |
|---|---|
| `DATABASE_URL` | Local JSON. Otherwise `POSTGRES_URL`, then `POSTGRES_PRISMA_URL`. |
| `OPENAI_API_KEY` | Overlaps are scored with a local word list. |
| `OPENAI_EMBEDDING_MODEL` | `text-embedding-3-small` |
| `VAPID_PUBLIC_KEY` / `VAPID_PRIVATE_KEY` / `VAPID_SUBJECT` | Locally, `data/vapid.json` is created automatically. |
| `TELEGRAM_BOT_TOKEN` / `TELEGRAM_BOT_USERNAME` / `TELEGRAM_WEBHOOK_SECRET` | Telegram alerts stay off. |
| `ENABLE_TEST_AGENTS` | Test entry is on locally and off in deployment. |

Generate push keys with `npx web-push generate-vapid-keys`. `VAPID_SUBJECT` starts with `mailto:`.

## Screens

- `/` enter
- `/join` create a node
- `/usershow` the grove
- `/my-node` your star and the people who overlap you
- `/devshow` the exhibition screen

## Not in this repo

API keys, database URLs, push secrets, participant sentences, and emails are not committed. On a deploy they belong only in environment variables.
