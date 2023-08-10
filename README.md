## About

GitHub Action to build and push a Docker image to the GitHub Container Registry without fuss.

The repository must contain a Dockerfile which will then be build and published as a package to the repository.

## Example usage

```yml
name: Docker Build

on:
  push:
    branches:
    - master

permissions:
  contents: read
  packages: write

jobs:
  docker-build:
    runs-on: ubuntu-latest
    if: github.repository_owner == 'e621ng' # Prevent builds starting in forks

    steps:
      - name: Publish to ghcr
        uses: e621ng/publish-to-ghcr@v1
```

There are no configuration parameters. 
