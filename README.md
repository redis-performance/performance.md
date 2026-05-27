# performance.md

Meta-repository for the [redis-performance](https://github.com/redis-performance) GitHub org. All projects are registered as git submodules.

## Projects & Docker images

| Project | Description | Docker image |
|---------|-------------|--------------|
| [go-ycsb](https://github.com/redis-performance/go-ycsb) | YCSB port in Go — multi-database workload benchmarks | [`redis/go-ycsb`](https://hub.docker.com/r/redis/go-ycsb) |
| [redis-benchmark-go](https://github.com/redis-performance/redis-benchmark-go) | redis-benchmark clone with rate limiting and client-side caching | [`redis/redis-benchmark-go`](https://hub.docker.com/r/redis/redis-benchmark-go) |
| [pubsub-sub-bench](https://github.com/redis-performance/pubsub-sub-bench) | Redis Pub/Sub subscriber throughput and latency benchmark | [`redis/pubsub-sub-bench`](https://hub.docker.com/r/redis/pubsub-sub-bench) |
| [vector-db-benchmark](https://github.com/redis-performance/vector-db-benchmark) | Vector DB benchmarking suite (Redis, Weaviate, Milvus, Qdrant, …) | [`redis/vector-db-benchmark`](https://hub.docker.com/r/redis/vector-db-benchmark) |
| [sidekiq-benchmark](https://github.com/redis-performance/sidekiq-benchmark) | Sidekiq protocol load benchmark — job throughput and latency (p50→p99.99) | [`redis/sidekiq-benchmark`](https://hub.docker.com/r/redis/sidekiq-benchmark) |
| [geo-bench](https://github.com/redis-performance/geo-bench) | Redis geo-command benchmarks | — |
| [redis-zbench-go](https://github.com/redis-performance/redis-zbench-go) | Sorted-set benchmark | — |
| [redis-benchmark-connect](https://github.com/redis-performance/redis-benchmark-connect) | TLS/mTLS connection benchmark | — |
| [redisbench-admin](https://github.com/redis-performance/redisbench-admin) | Benchmark automation and result management | — |
| [perf_data_converter](https://github.com/redis-performance/perf_data_converter) | Linux perf data format converter | — |
| [topdown-profiler](https://github.com/redis-performance/topdown-profiler) | Top-down microarchitectural profiling tool | — |

> All Docker images target `redis:8.6` or newer as the Redis dependency.

## Efforts log

| Date | What |
|------|------|
| 2026-05-27 | Docker Hub Overview descriptions created for all 5 published images |
| 2026-05-27 | CI/Docker Hub badges added to READMEs of all Docker-publishing repos |
| 2026-05-27 | `redis-benchmark-connect` CI unblocked: deprecated `ubuntu-20.04` runner replaced with `ubuntu-22.04` |
| 2026-05-26 | Docker Hub credentials rotated; docker-publish CI verified green across all repos |
| 2026-05-26 | Node24 GitHub Actions migration completed across all 16 active CI repos |
| 2026-05-26 | `sidekiq-rs` CI unblocked: replaced deprecated `supercharge/redis-github-action` with service container |
| 2026-05-26 | Bazel 9 compatibility fixed in `perf_data_converter` (pinned to Bazel 8, added explicit rule loads) |
| 2026-05-26 | Redis image references updated to `redis:8.6` across all Dockerfiles and CI configs |
| 2026-05-26 | YAML parse error fixed in `redis-benchmarks-specification` test suite |

## Usage

```bash
# Clone all submodules (shallow)
git submodule update --init --depth 1

# Apply a command across every submodule
git submodule foreach '<your command here>'
```

## Templates

`templates/CONTRIBUTING.md` and `templates/AGENTS.md` are the org-wide baseline pushed to every repo.
