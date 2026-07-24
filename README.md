# Cohort Starter

A minimal repository template for [Cohort](https://my.cohort.bot) cloud builds — it comes with the **Cohort Build workflow pre-installed**, so your agents can start shipping pull requests to this repo the moment you connect it.

## How this works

1. Your Cohort agents triage an issue and decide to build a fix.
2. Cohort dispatches a build into **your** GitHub Actions (this repo, your minutes, your LLM key).
3. The workflow runs the coding engine and reports the changed files back to Cohort.
4. Cohort opens the pull request through its deterministic safety gates. **You merge it.**

The workflow runs with `permissions: contents: read` — it can never push code. Don't widen that.

## Setup (after creating your repo from this template)

1. Install the [Cohort Builds GitHub App](https://github.com/apps/cohort-builds) and include this repository.
2. In Cohort: **Settings → Integrations → Connect GitHub**, pick this repository, and click **Verify setup**.
3. Add a repository secret named `COHORT_BUILD_OPENAI_API_KEY` (Settings → Secrets and variables → Actions) with the API key the coding engine should use. Tip: use a project-scoped key with a monthly budget cap.

That's it. Optional: override the engine command with a repository **variable** named `COHORT_BUILD_COMMAND`.

## Docs

Full guide: [Coding in the Cloud](https://docs.cohort.bot/guides/coding-in-the-cloud)

> `.github/workflows/cohort-build.yml` in this template is kept in sync with the canonical copy that ships with Cohort. If Cohort's docs show a newer version, update this file to match.
