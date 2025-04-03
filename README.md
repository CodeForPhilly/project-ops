# project-ops

A machine-parsable directory of operational details for Code for Philly projects.

## Repository Structure

Each project is represented by a directory containing two YAML files:

- `development.yaml`: Contains the project's GitHub repository information
- `hosting.yaml`: Contains domain and deployment configuration details

### Development Configuration

The `development.yaml` file specifies the GitHub repository where the project's code is hosted. Example:

```yaml
repository: github.com/CodeForPhilly/example-project
```

See [.schemas/development.json](.schemas/development.json) for the complete schema.

### Hosting Configuration

The `hosting.yaml` file defines:

- Domain names and their registrar information
- Deployment environments (production/staging) and their URLs

Example:

```yaml
domains:
  - name: example.com
    registrar: namecheap-codeforphilly
    expiration: 2025-12-31

deployments:
  - name: production
    environment: cfp-live-cluster
    urls:
      - https://example.com
      - https://www.example.com
```

See [.schemas/hosting.json](.schemas/hosting.json) for the complete schema.

## Development

### Schema Validation

The repository includes JSON Schema definitions in the `.schemas/` directory that provide validation and autocompletion in VSCode while editing the YAML files with the "YAML" VSCode extension by Red Had installed.
