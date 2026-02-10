# avionhttp

Python library for integrating with Avi-on's backend API.

## Release Process

Releases are fully automated via GitHub Actions. Pushing a version tag triggers:

1. Build wheel and source tarball
2. Publish to PyPI (trusted publishing)
3. Create GitHub release with attached artifacts

### Steps

1. Bump version in `pyproject.toml`
2. Commit: `git commit -am "Bump to v0.X.0"`
3. Tag and push: `git tag v0.X.0 && git push && git push --tags`

The workflow `.github/workflows/workflow.yml` runs on `push: tags: ['v*']`.

## Usage

```python
from avionhttp import http_list_devices

devices = http_list_devices(email, password, host)
# Returns list of locations with device/group metadata
```

## Code Style

- Ruff for linting/formatting (`ruff check --fix src/`)
- mypy for type checking (`mypy src/`)
