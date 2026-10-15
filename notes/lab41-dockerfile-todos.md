# Lab 41 — Fill Dockerfile TODO Skeleton

## Step 1 — Skeleton

Create: `Dockerfile.skeleton`

FROM eclipse-temurin:21-jdk AS build

WORKDIR /workspace

COPY . .

RUN ./mvnw -B -DskipTests package

FROM eclipse-temurin:21-jre AS runtime

USER 10001

COPY --from=build /workspace/target/*.jar /app/app.jar

HEALTHCHECK CMD curl -f http://localhost:8080/actuator/health || exit 1

ENTRYPOINT ["java","-jar","/app/app.jar"]

## Step 2 — Fill blanks

Completed Skeleton:

```dockerfile
FROM eclipse-temurin:21-jdk AS build

WORKDIR /workspace

COPY . .

RUN ./mvnw -B -DskipTests package

FROM eclipse-temurin:21-jre AS runtime

USER 10001

COPY --from=build /workspace/target/*.jar /app/app.jar

HEALTHCHECK CMD*curl -f http://localhost:8080/actuator/health || exit 1

ENTRYPOINT ["java","-jar","/app/app.jar"]
