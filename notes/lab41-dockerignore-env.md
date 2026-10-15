Paste and complete this template
# Lab 41 — Plan .dockerignore and Env

## Step 1 — Ignore list

Draft `.dockerignore` candidates: `.git`, `target/`, `.env`, `*.tfstate`, `notes/`, IDE folders.

## Step 2 — Check the reference

Runtime config via env (DB URL, user, password)—never `ENV PASSWORD=...` in Dockerfile.

## Step 3 — .env.example

List keys only (no values): `SPRING_DATASOURCE_URL`, username, password placeholders, Java opts.

## Step 4 — Evidence path

Note where Lab 41 will store `docker images` / inspect commit to GitHub (no screenshots).

## Scope
Pre-lab only — do not finish the full lab in this exercise.
