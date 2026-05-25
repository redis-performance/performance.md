# performance.md

Meta-repository for the [redis-performance](https://github.com/redis-performance) GitHub org.

All repos are registered as git submodules. Use this repo to apply consistent rules, coding standards, and agent instructions across all projects.

## Cloning submodules

```bash
# Clone all submodules (shallow)
git submodule update --init --depth 1

# Clone a single submodule
git submodule update --init --depth 1 <name>
```

## Templates

`templates/CONTRIBUTING.md` and `templates/AGENTS.md` are the org-wide baseline.
Per Benjamin Renaud's All Hands directive, every repo must have both files.

### Current status (as of 2026-05-25)

| File             | Has it                                              | Missing (30+ repos) |
|------------------|-----------------------------------------------------|---------------------|
| CONTRIBUTING.md  | openllmetry                                         | all others          |
| AGENTS.md        | redisbench-admin, topdown-profiler, memtier_benchmark | all others        |

### Pushing templates to all repos

```bash
# One-shot: copy templates to every submodule and open a PR
git submodule foreach '
  branch="chore/add-contributing-and-agents"
  git checkout -b "$branch" 2>/dev/null || git checkout "$branch"
  cp "$toplevel/templates/CONTRIBUTING.md" CONTRIBUTING.md
  cp "$toplevel/templates/AGENTS.md" AGENTS.md
  git add CONTRIBUTING.md AGENTS.md
  git diff --cached --quiet || git commit -m "Add CONTRIBUTING.md and AGENTS.md"
  git push origin "$branch"
  gh pr create --title "Add CONTRIBUTING.md and AGENTS.md" \
    --body "Adds baseline contribution and agent guidelines per org standards." \
    --base main --head "$branch" 2>/dev/null || true
'
```

> Repos where a file already exists will be overwritten — review diffs before merging.

## Applying any change across all repos

```bash
git submodule foreach '<your command here>'
```
