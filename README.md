# agentic-toolbox-misc

Public holding area for material that is not cleared for the work-safe
[agentic-toolbox](https://github.com/alexderz/agentic-toolbox).

This repository does not grant a blanket license. A file is here so it can
be read in public, not because its upstream license is settled.

## minecraft-builder

`skills/minecraft-builder` is a Bedrock block catalog derived from
[PrismarineJS/minecraft-data](https://github.com/PrismarineJS/minecraft-data).
That upstream has no LICENSE file, and the GitHub license field is null.
Do not copy this skill back into the work-safe toolbox until that upstream
has a permissive license file.

Read [skills/minecraft-builder/SKILL.md](skills/minecraft-builder/SKILL.md).
The catalog is `skills/minecraft-builder/references/blocks.json`. Numeric
protocol state ids are omitted on purpose.

## pr-lens

[skills/pr-lens/SKILL.md](skills/pr-lens/SKILL.md) renders PR diagrams using the pinned @coldtea/pr-lens-cli@0.8.1. The skill rewrite is MIT licensed; see its scoped [LICENSE](skills/pr-lens/LICENSE) and [provenance](SOURCES.md). The CLI installs an ISC-licensed yaml dependency at runtime. This move does not change that dependency or grant a blanket license to this repository.
[iris/](iris/) holds the notes copied unchanged from [grok-bot-perm docs/iris](https://github.com/alexderz/grok-bot-perm/tree/main/docs/iris).

## model-testing

[model-testing/](model-testing/) holds short notes that go with
[agentic-model-testing](https://github.com/alexderz/agentic-model-testing): which local models and engines to run,
from the latest grades. Start with [24gb-gpu-picks.md](model-testing/24gb-gpu-picks.md).

[model-testing/iris-followups/](model-testing/iris-followups/) holds Model Master's follow-ups on the Iris notes:
what got downloaded and tested, and what the tech bookmarks would take to try locally.
