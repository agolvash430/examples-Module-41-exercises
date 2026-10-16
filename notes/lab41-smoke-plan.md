# Lab 41 — Plan Container Smoke

## Step 1 — Steps

Planned Smoke Test Order:

1. Start the container.
2. Verify readiness endpoint reports READY.
3. Create or retrieve customer fixture CUS-1001.
4. Send request using correlation header:
   - X-Correlation-ID: lab-request-001
5. Verify application response and log correlation.
6. Capture smoke-test evidence.
7. Stop the container gracefully.
8. Verify clean container shutdown.

Expected Outcome:

- Readiness check succeeds.
- Customer fixture CUS-1001 is accessible.
- Correlation ID lab-request-001 appears in expected logs.
- Container shuts down without errors.

## Step 2 — Check the reference

Evidence Requirements:

- Store smoke-test logs under lab-41 notes.
- Store readiness-check evidence under lab-41 notes.
- Store request/response evidence under lab-41 notes.
- Use lab-generated test data only.
- Do not collect production data dumps.
- Do not use production screenshots.
- Document results for later review.

Example Paths:

```text
notes/lab-41/smoke-test.log
notes/lab-41/readiness-check.txt
