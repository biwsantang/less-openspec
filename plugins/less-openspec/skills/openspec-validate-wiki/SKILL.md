---
name: openspec-validate-wiki
description: Validate wiki Markdown against the Less OpenSpec OKF 0.2 contract. Use when the user asks to check, repair-plan, or review the format and provenance of repository planning artifacts.
---

# Validate an OKF wiki

Read [the shared artifact model](../references/artifact-model.md). This is a
read-only review unless the user explicitly asks to repair the reported issues.

1. Inspect every Markdown file under `wiki/`.
2. Treat `wiki/index.md` and `wiki/log.md` as reserved. If the root index
   exists, require its front matter to contain only `okf_version: "0.2"`.
3. For every other Markdown file, require parseable YAML front matter and a
   non-empty `type`. Accept descriptive types and unknown additional fields.
4. Check that each `status` is `draft`, `stable`, or `deprecated`; generated
   and verified timestamps are ISO 8601 values; and every `sources` item has a
   `resource`.
5. When the body uses a `[^source-id]` footnote for provenance, confirm that it
   matches a `sources[].id`. Report unused source IDs as a warning, not a hard
   failure.
6. Check relative links and artifact paths. Report broken links without
   declaring the wiki non-conformant solely because a target is unavailable.
7. Report pass/fail findings by file, distinguishing strict OKF errors from
   advisory discoverability or provenance improvements.

Do not add metadata, change a status, or manufacture sources or verification
evidence during validation. If repairs are authorized, preserve unknown front
matter fields and make the smallest compliant edit.
