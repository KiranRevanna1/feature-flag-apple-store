---
name: Feature Flag Apple Store
slug: feature-flag-apple-store
description: This template uses Edge Config as fast storage to control whether an store is open or closed.
framework: Next.js
useCase:
  - Edge Functions
  - Edge Config
css: Tailwind
deployUrl: https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Fvercel%2Fexamples%2Ftree%2Fmain%2Fedge-functions%2Ffeature-flag-apple-store&project-name=feature-flag-apple-store&repo-name=feature-flag-apple-store
demoUrl: https://edge-functions-feature-flag-apple-store.vercel.app/
relatedTemplates:
  - maintenance-page
  - ab-testing-simple
  - nextjs-boilerplate
---

# Apple Store

This template uses Edge Config as fast storage to control whether the store is open or closed.

## Demo

https://edge-functions-feature-flag-apple-store.vercel.app/

## How to Use

You can choose from one of the following two methods to use this repository:

### One-Click Deploy

After [setting up your environment variables](#set-up-environment-variables), deploy the example using [Vercel](https://vercel.com?utm_source=github&utm_medium=readme&utm_campaign=vercel-examples):

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Fvercel%2Fexamples%2Ftree%2Fmain%2Fedge-functions%2Ffeature-flag-apple-store&project-name=feature-flag-apple-store&repo-name=feature-flag-apple-store)

### Clone and Deploy

Execute [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app) with [npm](https://docs.npmjs.com/cli/init) or [Yarn](https://yarnpkg.com/lang/en/docs/cli/create/) to bootstrap the example:

```bash
npx create-next-app --example https://github.com/vercel/examples/tree/main/edge-functions/feature-flag-apple-store
# or
yarn create next-app --example https://github.com/vercel/examples/tree/main/edge-functions/feature-flag-apple-store
```

#### Set up environment variables

Copy the `.env.example` file in this directory to `.env.local` (which will be ignored by Git):

```bash
cp .env.example .env.local
```

This example requires you to set up an Edge Config and store its connection string in the `EDGE_CONFIG` environment variable. Fill the Edge Config you create with this content:

```json
{ "featureFlagsAppleStore_storeClosed": true }
```

Next, run Next.js in development mode:

```bash
npm install
npm run dev

# or

yarn
yarn dev
```

Deploy it to the cloud with [Vercel](https://vercel.com/new?utm_source=github&utm_medium=readme&utm_campaign=edge-middleware-eap) ([Documentation](https://nextjs.org/docs/deployment)).

## Opening / Closing the Store

You can control whether the store is open or not by changing the value of `featureFlagsAppleStore_storeClosed`. Use API routes or Vercel's Edge Config UI to update Edge Config.

> Note that you need to provide your own `TEAM_ID_VERCEL` and `AUTH_BEARER_TOKEN` environment variables in `.env.local` if you want to open or close the store as shown below.

To open the store go to:

```
http://localhost:3000/api/store/open
```

To close the store go to:

```
http://localhost:3000/api/store/close
```

Alternatively you can use the Edge Config UI in your Vercel dashboard to update the `featureFlagsAppleStore_storeClosed` value directly.
