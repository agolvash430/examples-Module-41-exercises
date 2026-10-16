# Lab 41 — Digest vs Latest

## Step 1 — Define

An image digest is an immutable cryptographic identifier (for example, a SHA-256 hash) that uniquely references a specific container image version.

A mutable tag such as `:latest` can be reassigned to different image versions over time, which means the image pulled today may not be the same image pulled later.

## Step 2 — Check the reference

- Lab 42 and Lab 44 promote container images by digest.
- Digest-based promotion ensures the exact same image is deployed across environments.
- The `:latest` tag can drift between staging and production.
- Using digests improves deployment reproducibility and traceability.
- Release decisions should reference a specific digest rather than a mutable tag whenever possible.

## Step 3 — CRM example

Example application tag:

```text
crm-api:lab41
