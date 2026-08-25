# Serving Stack

The one system this course builds.

## What Is Here

```text
app/        empty. Your service goes here, starting Week 2 Day 2
docs/       the API contract the Agentic AI cohort integrates against
scripts/    verify-env.sh, which checks your machine against what the labs need
PINS.md     every version this course depends on
setup.md    how to work in this repository
```

That is the whole repository, and the shortness of that list is the point.

You are not given a finished system to read. You build one, a day at a time, and by Week 6 another cohort's agents are calling it.

## What You Add, and When

| Week | Day | What You Add |
|---|---|---|
| 2 | Mon | `app/` behind an OpenAI-compatible `/v1` on CPU |
| 2 | Tue | `Dockerfile`, and your image on Docker Hub |
| 2 | Wed | `Dockerfile.gpu`, the same code on a GPU |
| 2 | Thu | `compose.yaml`, the stack described rather than run by hand |
| 3 | Thu | `bench/`, the harness that measures all of it |

Each one is a lab, and each one starts from files that day hands you.

Lab instructions, decks and quizzes are on the course Drive, one folder per week. This repository is your code.

## Docker Image Sizes — Week 2, Tue

Naive Dockerfile (`python:3.11` full base, no `--no-cache-dir`) vs the slim Dockerfile (`python:3.11-slim`, CPU-only PyTorch wheels, `--no-cache-dir`).

Neither image contains model weights; those live in a mounted volume.

| Stage | Image Size |
|---|---:|
| Naive build (full base, cached pip) | 16.5 GB |
| Slim CPU build | 1.61 GB |

## Start Here

Run:

```bash
./scripts/verify-env.sh
```

This checks your machine and writes:

```text
verify-env-report.json
```

Then read:

```text
setup.md
```

It is short, and it covers the two things that go wrong:

- Committing a key
- Committing a model
