# Lab 41 — Sketch Multi-Stage Build

## Reference

| Stage | Contains | Must not contain |
| --- | --- | --- |
| build | JDK 21, Maven, sources | runtime secrets |
| runtime | JRE, app JAR, non-root user | Maven, .git, passwords |

## Step 1 — Stages

### Stage 1: build

Purpose:
- Compile and package the Spring CRM application.

Contains:
- JDK 21
- Maven / Maven Wrapper
- Application source code
- pom.xml
- Resources and tests

Output:
- Packaged application JAR

### Stage 2: runtime

Purpose:
- Run the packaged Spring CRM application.

Contains:
- JRE 21
- Application JAR
- Non-root application user

Copied from build stage:
- Application JAR only

Not copied:
- Source code
- Maven binaries
- Build cache
- Test artifacts
- Git metadata

## Step 2 — Check the reference

Runtime image requirements:

- Use a JRE 21 runtime image.
- Prefer Eclipse Temurin / Temurin-based JRE images as instructed.
- Copy only the packaged application JAR from the build stage.
- Do not include Maven in the runtime image.
- Do not include source code in the runtime image.
- Do not include the `.git` directory in the runtime image.
- Do not include passwords, tokens, secrets, or credentials in the runtime image.

Benefits:

- Smaller image size.
- Reduced attack surface.
- Faster deployments.
- Fewer unnecessary artifacts in production.

## Step 3 — User

Planned runtime user:

UID: 10001

Example plan:

- Create application user with UID 10001.
- Run the Spring CRM application as UID 10001.
- Avoid running the container as root.

Why root fails the lab:

- Root provides unnecessary privileges inside the container.
- A compromised application would gain elevated permissions.
- Running as a non-root user follows least-privilege principles.
- The lab requires a non-root runtime configuration.

## Step 4 — CRM note

Customer fixtures `CUS-1001` and `CUS-1002`
