# GitHub Actions Workflows

## data-pr-checks.yml

Runs all required PR checks for the CDC Lakehouse assignment on every pull request and push to `main`.

| Job | Purpose |
|-----|---------|
| `lint-python-or-sql` | Formatting and code quality (`ruff`, `black`, `sqlfluff`) |
| `test-pipeline` | Unit and integration tests (`pytest`) |
| `validate-models` | dbt model validation (`dbt parse`, `dbt test`) |
| `schema-contract-check` | Schema compatibility checks |
| `data-quality-check` | Business and system validation rules |
| `catalog-check` | Catalog metadata validation |
| `security-and-secrets-scan` | Dependency audit and secrets scan (`pip-audit`, `bandit`, `gitleaks`) |

All 7 jobs should be set as required status checks in branch protection rules before merge.
