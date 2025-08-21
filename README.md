# Run Playwright

[![Release](https://img.shields.io/github/v/release/phi-ag/run-playwright?style=for-the-badge)](https://github.com/phi-ag/run-playwright/releases)
[![Check](https://img.shields.io/github/actions/workflow/status/phi-ag/run-playwright/check.yml?style=for-the-badge&label=check)](https://github.com/phi-ag/run-playwright/actions/workflows/check.yml)

Run [Playwright](https://github.com/microsoft/playwright) container action

## Usage

```yaml
steps:
  - name: Run Playwright
    uses: phi-ag/run-playwright@v1
    env:
      BASE_URL: https://example.com
    with:
      options: -v ${STORE_PATH}:${STORE_PATH}
      run: |
        corepack enable
        corepack prepare --activate

        pnpm config set store-dir ${STORE_PATH}
        pnpm install --frozen-lockfile
        pnpm test:e2e
```

Use a specific version, see [available image tags](https://mcr.microsoft.com/en-us/product/playwright/tags)

```yaml
steps:
  - name: Run Playwright
    uses: phi-ag/run-playwright@v1
    env:
      BASE_URL: https://example.com
    with:
      version: v1.55.0-noble@sha256:b27e719ecbfef153e13fd24e8341736733bf2658b229677eb21ff57ff5d7fb29
      run: |
        echo hello world
```

If this action doesn't work for you take a look at the [official recommendation](https://github.com/microsoft/playwright-github-action) or use something like this

```yaml
steps:
  - name: Run Playwright
    uses: docker://mcr.microsoft.com/playwright:v1.47.2
    with:
      args: ./e2e/run.sh
```
