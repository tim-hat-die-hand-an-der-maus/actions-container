# actions-container

This repository contains a set of reusable workflows geared towards building and working with
container images.

The project follows semantic versioning. You can depend on tags for specific versions of use a
major version tag (e.g. `v1`).

Every commit on the main branch leads to a new release. Releases are managed by
[commitizen][commitizen], which relies on [conventional commits][ccommit]. To make sure you don't
accidentally create commits with an unconventional message, install a pre-commit hook using
`make pre-commit`.

[commitizen]: https://commitizen-tools.github.io/commitizen/

[ccommit]: https://www.conventionalcommits.org/en/v1.0.0/

## Example

```yaml
jobs:
  build-container-image:
    uses: BlindfoldedSurgery/actions-container/.github/workflows/build-image-docker.yml@v1
    with:
      push-image: false
```

## Available jobs

### build-image-docker

Build a container image using Docker and optionally publish it to the repo's container registry.

The current commit's SHA-digest is passed to the build as a build-arg called `APP_VERSION`.

**Inputs:**

| Name       | Required |            Default            |      Example      | Description                                                    |
|:-----------|:--------:|:-----------------------------:|:-----------------:|----------------------------------------------------------------|
| push-image |   yes    |                               |  `true`/`false`   | Whether to push the resulting container image to the registry. |
| image-name |    no    | The slugified repository name | `my-cool-project` | The container image name (without the tag)                     |

### clean

Build a container image using Docker and optionally publish it to the repo's container registry.

The current commit's SHA-digest is passed to the build as a build-arg called `APP_VERSION`.

**Inputs:**

| Name                 | Required |            Default            |      Example      | Description                                   |
|:---------------------|:--------:|:-----------------------------:|:-----------------:|-----------------------------------------------|
| image-name           |    no    | The slugified repository name | `my-cool-project` | The container image name (without the tag)    |
| min-versions-to-keep |    no    |             `10`              |                   | The number of most recent versions to keep.   |
| continue-on-error    |    no    |            `true`             |  `true`/`false`   | See [GitHub Actions docs][continue-on-error]. |

[continue-on-error]: https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions#jobsjob_idcontinue-on-error
