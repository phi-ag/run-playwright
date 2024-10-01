# Run Playwright

[![Release](https://img.shields.io/github/v/release/phi-ag/run-playwright?style=for-the-badge)](https://github.com/phi-ag/run-playwright/releases)

Run [Playwright](https://github.com/microsoft/playwright) container action

## Usage

```yaml
steps:
  - name: Run Playwright
    uses: phi-ag/run-playwright@v0
    with:
      run: |
        echo hello
        echo world
```

Use a specific version, see [available image tags](https://mcr.microsoft.com/en-us/product/playwright/tags)

```yaml
steps:
  - name: Run Playwright
    uses: phi-ag/run-playwright@v0
    with:
      version: v1.47.2
      run: |
        echo hello
        echo world
```
