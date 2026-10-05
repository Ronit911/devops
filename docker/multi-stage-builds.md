# Multi-Stage Docker Builds

Multi-stage builds allow a Dockerfile to use multiple build stages.

This is particularly useful for applications that require a build environment but only need the resulting artifacts at runtime.

## The Problem

A build environment may require:

- Development dependencies
- Compilers
- Build tools
- Package managers
- Source code

The production application may not need all of these components.

Including everything in the final image can make the image unnecessarily large.

## Multi-Stage Approach

A simplified structure is:

Build Stage
    |
    v
Install dependencies
    |
    v
Build application
    |
    v
Production Stage
    |
    v
Copy required output
    |
    v
Runtime image

## Example

FROM node:24-alpine AS builder

WORKDIR /app

COPY package*.json ./

RUN npm ci

COPY . .

RUN npm run build


FROM node:24-alpine AS runner

WORKDIR /app

COPY --from=builder /app/dist ./dist

CMD ["node", "dist/server.js"]

The exact structure depends on the framework and application.

## Benefits

Multi-stage builds can:

- Reduce final image size
- Keep build tools out of production
- Reduce unnecessary dependencies
- Improve separation between build and runtime environments

## Security Consideration

The final image should contain only what is required to run the application whenever practical.

Avoid unnecessarily copying:

- Source files
- Development dependencies
- Build caches
- Credentials
- Local configuration files

## Dockerignore

A .dockerignore file can prevent unnecessary files from being sent as part of the Docker build context.

Example entries:

node_modules
.git
.env
npm-debug.log

The exact contents should depend on the application.

## Production Principle

A useful production image should be:

Small
+
Reproducible
+
Minimal
+
Focused on runtime
