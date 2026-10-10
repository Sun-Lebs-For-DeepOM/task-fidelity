# Validation scope — v0.1.0

Release date: 2026-10-10.

This is the first public instruction-only release.

The release preparation checks:
- Skill frontmatter and naming with the Skill Creator validator.
- Existence of the referenced local files.
- UTF-8 decoding, LF line endings, and absence of unfinished scaffold content.
- Public file scope and absence of machine-specific paths, credentials, or private task transcripts.
- The exact files selected for the initial Git commit.

These checks establish packaging facts. They do not establish a measured reduction in task drift. The examples in this repository are illustrative, not model performance results.

Behavioral evaluation should inspect the original task, actual actions, and resulting artifacts. It should include repeated corrections, preserved constraints, recovery from summaries, and simple tasks that should not incur unnecessary clarification. Compare the same task and model conditions, and record both task quality and additional effort.

No improvement percentage, universal success rate, or cross-client performance claim is made by this release.
