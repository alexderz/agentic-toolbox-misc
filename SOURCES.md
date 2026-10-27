# Sources

## pr-lens

Migrated from alexderz/agentic-toolbox, skills/pr-lens. The rewrite remains MIT; see [its license](skills/pr-lens/LICENSE). This grants no license to other skills here.

| Skill | Upstream | Pin | License | Notes |
| --- | --- | --- | --- | --- |
| pr-lens | coldteadotai/pr-lens (`skills/pr-lens`) | 09f6378c082ff8ddb17e211f36bfc71c2f2b8d86 (intent pin; body rewrite) | MIT upstream / rewrite | Opt-in; operator asks. Local render + PR attach only (no `canvas`, no `analyze`). CLI pinned exactly `@coldtea/pr-lens-cli@0.8.1`; every new release is a one-line SOURCES bump with a security read (no automatic patch releases). SKILL only; references linked at the pin, not vendored. No `scripts/`. CLI subcommands allowlisted to `validate` and `render`. The CLI's transitive dependencies float (`npx` uses no lockfile). Scanner waived by maintainer for DER-274 (scanner work: DER-273); manual security read done. Compared with upstream at Monthly. Wording edit DER-288, pins unchanged; security-cleared 2026-09-27. |

The CLI is installed at runtime, not vendored. Its yaml dependency is ISC licensed. ISC is permissive, not GPL; this skill is kept outside the work-safe toolbox under that repository’s dependency policy.
