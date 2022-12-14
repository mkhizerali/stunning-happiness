# Store app builds on Contentful + Shopify Hydrogen

Hydrogen is a React framework and SDK that you can use to build fast and dynamic Shopify custom storefronts.

Contentful is the most flexible and easy headless CMS that can power up your customer shopping experience with flexible content models, and field editors for authors to collaborate and manage content.

## What's in this app (dev eye)

- Styling with [Tailwind](https://tailwindcss.com/)
- End-to-end testing with [Playwright](https://playwright.dev)
- Unit testing with [Vitest](https://vitest.dev) and [Testing Library](https://testing-library.com)
- Code formatting with [Prettier](https://prettier.io)
- Javascript linting with [ESLint](https://eslint.org) and the Hydrogen [ESLint plugin](https://github.com/Shopify/hydrogen/tree/main/packages/eslint-plugin)
- Contentful

## Getting started

**Requirements:**

Add your Contentful space Id and preview access token to `.env`

```
CONTENTFUL_SPACE_ID=YOUR_SPACE_ID
CONTENTFUL_ACCESS_TOKEN=YOUR_PREVIEW_ACCESS_TOKEN
```

- Node.js version 16.5.0 or higher
- Yarn

```bash
yarn
yarn dev
```

**Optionally** you can pre-fill your Contentful empty space with Content:

Install contentful cli and import `./contentful-export.json` content.

In the project root folder run the following in your terminal:

```bash
npm i -g contentful-cli
# Then
contentful space import --space-id YOUR_SPACE_ID --content-file ./contentful-export.json
```

Remember to update `hydrogen.config.js` with your shop's domain and Storefront API token!

---

## Previewing a production build

To run a local preview of your Hydrogen app in an environment similar to Oxygen, build your Hydrogen app and then run `yarn preview`:

```bash
yarn build
yarn preview
```

## Building for production

```bash
yarn build
```

## Running tests

This project contains basic end-to-end (E2E) tests in the `/tests/e2e` folder powered by [Vitest](https://vitest.dev).

You can run tests in development, and they will automatically reload when you make changes to the component you provide to `hydrogen.watchForUpdates()`:

```bash
yarn test
```

To run tests in a continuous-integration (CI) environment like GitHub Actions:

```bash
yarn test:ci
```
