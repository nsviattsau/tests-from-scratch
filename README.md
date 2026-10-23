![CI](https://github.com/nsviattsau/tests-from-scratch/actions/workflows/ci.yml/badge.svg)

# tests-from-scratch

A full testing pyramid built from scratch on a small user-management app (Node/Express API + React and Angular front-ends), wired into a GitHub Actions pipeline.

## What is tested

| Layer | Tools | Where |
|---|---|---|
| API / unit | Jest, ts-jest, Supertest | `packages/node/__tests__` |
| Front-end components | Jest, React Testing Library, MSW (API mocking) | `packages/react-app/src/__tests__` |
| End-to-end | Playwright on Chromium, Firefox and WebKit (traces, screenshots and video on failure) | `e2e/tests` |
| CI/CD | GitHub Actions: lint, backend tests, frontend tests with coverage, E2E | `.github/workflows/ci.yml` |

## Stack

TypeScript · Node.js / Express · React · Angular · Yarn workspaces (monorepo) · ESLint

## Run it

```bash
corepack enable
yarn install

yarn workspace node test        # API tests with coverage
yarn workspace react-app test   # React component tests
yarn e2e                        # Playwright E2E (starts backend and frontend automatically)
```
