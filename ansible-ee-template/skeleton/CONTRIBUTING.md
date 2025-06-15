# Contributing Guide

Thank you for your interest in contributing to this Ansible Execution Environment project!

## Development Process

1. **Fork the repository**
2. **Create a feature branch**
3. **Make your changes**
   - Update the execution environment configuration (`execution-environment.yml`)
   - Add dependencies to appropriate files (`requirements.txt`, `requirements.yml`, `bindep.txt`)
   - Test your changes locally
4. **Submit a Pull Request**

## Adding Dependencies

### Python Packages

Add Python packages to `requirements.txt`:

```
# Example
requests>=2.28.0
```

### Ansible Collections

Add Ansible collections to `requirements.yml`:

```yaml
collections:
  - name: community.docker
    version: ">=3.0.0"
```

### System Packages

Add system packages to `bindep.txt`:

```
# Example
rsync [platform:rpm]
```

## Testing Your Changes

Before submitting a PR, please test your changes:

```bash
# Build the image
make build

# Test the image
make test
```

## Versioning

We use Semantic Versioning. Version format is `MAJOR.MINOR.PATCH`:
- MAJOR: Incompatible changes
- MINOR: New functionality in a backward-compatible manner
- PATCH: Backward-compatible bug fixes

## Release Process

1. Update version reference in documentation if applicable
2. Tag the commit with the new version: `git tag -a v1.0.0 -m "Release v1.0.0"`
3. Push the tag: `git push origin v1.0.0`
4. CI will automatically create a release and build/publish the container image
