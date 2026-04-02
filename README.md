# skeleton-playwright-typescript

Skeleton UI test framework using Playwright and TypeScript. Browsers are bundled inside the Docker image so no separate browser setup is needed.

## Project structure

| File/Folder | What it is |
|---|---|
| `Dockerfile` | Builds the test image — starts from the official Playwright image which includes browsers, then installs dependencies |
| `package.json` | Lists the npm packages the project depends on |
| `playwright.config.ts` | Configuration — base URL, browser, headless mode. Reads from `.env` |
| `.env` | Environment variables for local runs — base URL and headless toggle |
| `tsconfig.json` | Tells TypeScript how to compile the code |
| `tests/sample.spec.ts` | One sample test — navigates to the base URL and checks the page title is not empty |
| `.devcontainer/devcontainer.json` | Dev container configuration for VS Code — includes Docker so you can run builds from inside it |

## Build and run

```bash
docker build -t skeleton-playwright . && docker run --rm skeleton-playwright
```

## Configuration

To change the base URL or other settings without editing files, pass environment variables:

```bash
docker run --rm -e BASE_URL=https://your-site.com skeleton-playwright
```
