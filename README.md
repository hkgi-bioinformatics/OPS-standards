# HKGI OPS public schemas

Static site for the public JSON Schemas of the HKGI OPS data platform. GitHub Pages publishes this repository as-is. Schema documents stay at stable, versioned paths.

## Published schemas

| Schema | Version | Path |
| --- | --- | --- |
| HKGI Dataset Submission Metadata Model | 1.0.0 | [`schemas/dataset-submission-metadata/1.0.0/schema.json`](schemas/dataset-submission-metadata/1.0.0/schema.json) |

A machine-readable list is at [`schemas/catalog.json`](schemas/catalog.json).

The dataset submission schema identifies itself as:

```text
https://hkgi.org/schemas/dataset-submission-metadata/1.0.0/schema.json
```

That `$id` matches the file in this repository. The previous identifier used a `.yaml` suffix; the document is JSON, so the suffix is `.json`.

## Enable GitHub Pages

After the GitHub repository exists and `main` has been pushed:

1. In the repository, open **Settings → Pages**.
2. Set **Source** to **GitHub Actions**.
3. Push to `main`, or run the **Deploy GitHub Pages** workflow.

The workflow in `.github/workflows/pages.yml` publishes the repository root. `.nojekyll` is present so GitHub does not run Jekyll over the schema files.

Until a custom domain is attached, the live URLs use the GitHub Pages host, for example:

```text
https://<owner>.github.io/<repository>/schemas/dataset-submission-metadata/1.0.0/schema.json
```

The schema `$id` uses `https://hkgi.org/...`. Those two hosts agree only after `hkgi.org` (or a path on it) serves this site. Add a `CNAME` file here only if this Pages site should be the site for that hostname. If `hkgi.org` already has another site, proxy `/schemas/` to Pages instead of claiming the whole domain.

## Add a schema version

1. Add the document at `schemas/<name>/<version>/schema.json`.
2. Set `$id` to the public URL of that file.
3. Add an entry to `schemas/catalog.json` and a card in `index.html`.
4. Leave released versions in place. Publish a change by adding a new version directory.
