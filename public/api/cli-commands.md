# CLI Commands

## `next-yc deploy`

Deploy Next.js application with one command.

```bash
next-yc deploy --project . --verbose
```

Executes the full pipeline: analyze, build, upload, terraform apply.

### Key options

- `--project <path>` / `-p` — path to the Next.js project
- `--output <dir>` / `-o` — output directory for build artifacts
- `--app-name <name>` — application name for deployment
- `--env <environment>` — deployment environment (e.g. production, staging)
- `--region <region>` — Yandex Cloud region
- `--assets-bucket <bucket>` — Object Storage bucket for static assets
- `--build-id <id>` — custom build identifier
- `--skip-build` — skip application build phase
- `--dry-run` — preview changes without applying
- `--verbose` — enable verbose output
- `--auto-approve` — skip Terraform apply confirmation

## `next-yc analyze`

Analyze a Next.js project and report detected capabilities.

```bash
next-yc analyze --project .
```

Detected capabilities:
- Next.js version (13.x-16.x)
- App Router usage
- Pages Router usage
- API routes
- ISR (on-demand revalidation, tags, paths)
- Middleware (edge-emulated mode)
- Server Actions
- Image optimization

## `next-yc build`

Build and package a Next.js project for Yandex Cloud deployment.

```bash
next-yc build --project .
```

## `next-yc upload`

Upload build artifacts to Yandex Cloud Object Storage.

```bash
next-yc upload --project .
```

## Environment variables

- `NYC_PROJECT` — path to project directory
- `NYC_OUTPUT` — output directory for build artifacts
- `NYC_REGION` — Yandex Cloud region
- `NYC_BUCKET` — Object Storage bucket name
- `NYC_APP_NAME` — application name
- `NYC_ENV` — deployment environment
- `NYC_ENV_*` — server environment values (e.g. `NYC_ENV_LOG_LEVEL=info`)
- `NYC_TF_VAR_*` — Terraform variable passthrough (e.g. `NYC_TF_VAR_memory_mb=512`)
- `NYC_SKIP_BUILD` — skip application build phase when set to `1`
- `NYC_VERBOSE` — enable verbose output when set to `1`
