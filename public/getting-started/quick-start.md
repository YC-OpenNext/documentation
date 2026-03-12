# Quick Start

```bash
npm install
next-yc deploy --project . --verbose
```

`next-yc deploy` executes project build automatically when `package.json` has a `build` script.

Default behavior is execution-enabled (analyze, build, upload, terraform apply).
For dry-run mode:

```bash
next-yc deploy --project . --dry-run --verbose
```

Runtime settings can be provided in `next-yc-cfg.json`:

```json
{
  "runtime": {
    "public": {
      "PUBLIC_API_BASE": "/api"
    },
    "env": {
      "LOG_LEVEL": "info"
    },
    "secrets": {
      "DB_URL": { "source": "lockbox", "secretId": "e6q..." }
    },
    "scope": {
      "LOG_LEVEL": ["ssr", "api"],
      "DB_URL": ["api"]
    }
  }
}
```
