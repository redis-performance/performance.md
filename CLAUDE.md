# performance.md

Meta-repository for the [redis-performance](https://github.com/redis-performance) GitHub org.

All repos are registered as git submodules. Use this repo to apply consistent rules, coding standards, and agent instructions across all projects.

## Cloning submodules

```bash
# Clone all submodules (shallow)
git submodule update --init --depth 1

# Clone a specific submodule
git submodule update --init --depth 1 <name>
```

## Applying changes across repos

Each submodule is an independent git repo. To push changes (e.g. a new CLAUDE.md) to all of them:

```bash
git submodule foreach 'git checkout -b <branch> && cp ../CLAUDE.md . && git add CLAUDE.md && git commit -m "..." && git push origin <branch>'
```
