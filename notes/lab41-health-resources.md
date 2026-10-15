# Lab 41 — Health and Resource Checklist

## Step 1 — Health

Expected readiness endpoint:

/actuator/health/readiness

What "ready" means:

- The Spring CRM application has started successfully.
- Required dependencies are available.
- Database connectivity has been verified.
- The application can accept requests from agents.
- Agents can successfully retrieve and update customer records such as CUS-1001 and CUS-1002.

## Step 2 — Check the reference

Readiness Policy:

- Readiness fails closed when the database is unavailable.
- The container should not report READY if required backend dependencies are unavailable.
- Agents should not receive a partially functional CRM experience.
- Traffic should only be routed to containers that are fully operational.

Example:

- CRM application running + database available = READY
- CRM application running + database unavailable = NOT READY

## Step 3 — Resources

Placeholder local Docker resource limits:

Memory Limit:
- 512 MB

CPU Limit:
- 1 CPU

Example docker run values:

--memory=512m
--cpus=1.0

Lab Notes:

- Values are placeholder defaults for pre-lab planning.
- Actual limits should be confirmed during the full Lab 41 exercise.

## Step 4 — Graceful stop

Upon receiving SIGTERM, the CRM application should stop accepting new requests and allow in-flight requests such as lab-request-001 to complete gracefully before shutdown.

## Scope

Pre-lab only — do not finish the full lab in this exercise.
