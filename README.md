# Aicoetpk Graph Supermemory

Aicoetpk is intended to become a repository knowledge and Graph Supermemory platform for ingesting Git repositories, ZIP archives, and local directories, then publishing cited project knowledge, reviewed translations, Mermaid mind maps, optional Graphity artefacts, repository-scoped MCP, chat, share links, administration, background processing, incremental updates, and authenticated messaging webhooks.

## Current implementation status

This public repository is presently a **Cloudflare Workers + D1 starter template**, not the complete Graph Supermemory product. The verified application currently executes `SELECT * FROM comments LIMIT 3` against a D1 database and renders the result as HTML. No product feature is described as implemented without source evidence.

See the evidence-backed capability matrix in [`docs/PRODUCT_STATUS.md`](docs/PRODUCT_STATUS.md). It separates current implementation, documented target design, generated knowledge, and planned work.

## Current starter behaviour

- Worker entry point: `src/index.ts`
- HTML renderer: `src/renderHtml.ts`
- D1 migration: `migrations/0001_create_comments_table.sql`
- Worker/D1 configuration: `wrangler.json`
- Package checks: `npm run check`

## Product direction

The intended architecture is described as a target, not a claim of completion:

- **Knowledge ingestion:** Git repositories, ZIP archives, and local directories.
- **Knowledge outputs:** truthful README summaries, project overviews, wiki/document catalogues, document content, reviewed multi-language translations, Mermaid mind maps, and optional Graphity artefacts.
- **Public discovery:** SEO-friendly repository routes at `/{owner}/{repo}`, `/{owner}/{repo}/mindmap`, and `/{owner}/{repo}/graphify`.
- **Access surfaces:** repository-scoped MCP, built-in chat, embedded chat APIs, and share links.
- **Administration:** repositories, users, roles, departments, API keys, AI providers/models, skills, MCP providers, and GitHub App imports.
- **Workers:** idempotent background ingestion, translation, mind-map, Graphity, and incremental-update processing.
- **Integrations:** authenticated Feishu, QQ, WeChat, and Slack webhook adapters.

Generated knowledge should always identify its source revision, generation time, citations, language, and review status. See [`docs/PRODUCT_STATUS.md`](docs/PRODUCT_STATUS.md) for the proposed contract and the next safe implementation slices.

## Development

Install dependencies:

```bash
npm install
```

Run type-checking and the Wrangler dry-run validation:

```bash
npm run check
```

Apply the migration locally and start the development server:

```bash
npm run dev
```

Deploy only after reviewing the Wrangler configuration and applying the migration to the intended D1 database:

```bash
npm run deploy
```

Do not commit `.env` files, API keys, OAuth tokens, cookies, private keys, credentials, or database dumps.

## Repository

- Public repository: <https://github.com/aiforfreecloud-sudo/aicoetpk>
- Product status snapshot: [`docs/PRODUCT_STATUS.md`](docs/PRODUCT_STATUS.md)
