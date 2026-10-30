# Getting started with AssemblyAI and Thally

A developer guide to using AssemblyAI and building documentation with Thally. The site gives you a short path from installing the AssemblyAI Python SDK to saving a transcript, then shows you how to build and publish a documentation site of your own.

**View the site:** [thally-demo.thally.app](https://thally-demo.thally.app/)

## What you’ll learn

- **Introduction:** What AssemblyAI does, who it’s for, and a short video tour of the site.
- **Quickstart:** Install the Python SDK, configure your API key, and transcribe a sample audio file. The example has been tested against the live AssemblyAI API.
- **YouTube podcast guide:** Paste an episode URL, download its audio, and save a transcript with timestamps and speaker labels.
- **Thally guide:** Create a documentation site, configure its navigation and identity, write MDX pages, and publish through GitHub and Thally Cloud.

## Run locally

You need Git, Node.js 22.14+ or 24+, and npm.

```bash
git clone https://github.com/writersblockchain/thally-demo.git
cd thally-demo
npm ci
npm run dev
```

Open [localhost:3040](http://localhost:3040). If the port is occupied, use `npm run dev -- --port 3041`.

You don’t need an AssemblyAI API key to run the documentation site. To execute the transcription examples, follow the quickstart and supply your own key with available credits. Keep credentials out of source files and Git.

## Edit the documentation

| Path | Purpose |
| --- | --- |
| `src/content/introduction.mdx` | Homepage and video introduction |
| `src/content/quickstart.mdx` | AssemblyAI SDK quickstart |
| `src/content/guides/` | Podcast transcription and Thally site-building guides |
| `docs.json` | Navigation and footer configuration |
| `src/data/site.ts` | Site identity and brand defaults |
| `public/` | Video and other static assets |

Every MDX page needs `title` and `description` frontmatter. Add new pages to `docs.json` so readers can find them. Read [AGENTS.md](AGENTS.md) for ownership and contribution rules; runtime-owned files and `starter-release.json` are managed by Thally’s update workflow.

## Validate and publish

Before pushing changes, run:

```bash
npm run check -- --ci
npm run typecheck
npm run build
```

This site is hosted by Thally Cloud. Push reviewed changes to the connected repository’s production branch (`main`) to trigger deployment. The Thally GitHub App must have access to the repository, and the repository and branch must match the site’s Cloud configuration.

Check **Deployments** in Thally Cloud for the expected commit and wait for it to become **Live**. Then verify the published page. You can also manage publishing in Cloud; the CLI’s `thally deploy` command targets self-hosted providers rather than this managed `thally.app` site.

## References

- [AssemblyAI documentation](https://www.assemblyai.com/docs)
- [Thally quickstart](https://docs.thally.io/quickstart)
- [Thally managed hosting](https://docs.thally.io/guides/managed-hosting)

## License

[MIT](LICENSE)
