# HKGI OPS public schemas

Static site for the public JSON Schemas of the HKGI OPS data platform. GitHub Pages publishes this repository as-is. Schema documents stay at stable, versioned paths.

## Published schemas

| Schema | Version | Path |
| --- | --- | --- |
| HKGI Dataset Submission Metadata Model | 1.0.0 | [`schemas/dataset-submission-metadata/1.0.0/schema.json`](schemas/dataset-submission-metadata/1.0.0/schema.json) |
| OPS build-release manifest | 1.0.0 | [`schemas/build-release/v1.0.0.schema.json`](schemas/build-release/v1.0.0.schema.json) |

A machine-readable list is at [`schemas/catalog.json`](schemas/catalog.json).

The dataset submission schema identifies itself as:

```text
https://hkgi-bioinformatics.github.io/OPS-standards/schemas/dataset-submission-metadata/1.0.0/schema.json
```

That `$id` is the GitHub Pages URL of this file.

The build-release schema is [schema version 1.0.0](schemas/build-release/v1.0.0.schema.json). It accepts the manifests the temporal worker and the registry service publish today. Those two repositories will vendor that file. This repository does not publish their images.

## Enable GitHub Pages

After the GitHub repository exists and `main` has been pushed:

1. In the repository, open **Settings → Pages**.
2. Set **Source** to **GitHub Actions**.
3. Push to `main`, or run the **Deploy GitHub Pages** workflow.

The workflow in `.github/workflows/pages.yml` publishes the repository root. `.nojekyll` is present so GitHub does not run Jekyll over the schema files.

The live schema URL is:

```text
https://hkgi-bioinformatics.github.io/OPS-standards/schemas/dataset-submission-metadata/1.0.0/schema.json
```

## Add a schema version

1. Add the document at `schemas/<name>/<version>/schema.json`.
2. Set `$id` to the public URL of that file.
3. Add an entry to `schemas/catalog.json` and a card in `index.html`.
4. Leave released versions in place. Publish a change by adding a new version directory.
