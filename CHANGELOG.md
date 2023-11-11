## v3.0.0 (2023-11-11)

### BREAKING CHANGE

- If you relied on the provenance metadata manifest,
this will break your build, because it disables the creation of that.

### Feat

- Add workflow to join multiple images into one
- Add option to store digests as artifact
- Provide image digest as build output
- Add possiblity to specify platform for build-image-docker

## v2.6.0 (2023-11-06)

### Feat

- Add input to specify additional build args
- Add input for target stage

## v2.5.1 (2023-10-21)

### Fix

- Respect image-name input in clean job

## v2.5.0 (2023-10-21)

### Feat

- Allow setting a custom version

### Fix

- Set up buildx in docker build job

## v2.4.0 (2023-10-21)

### Feat

- Allow setting a custom build context

## v2.3.2 (2023-10-21)

### Fix

- Remove typo in build tags expression

## v2.3.1 (2023-10-21)

### Fix

- Try using single quotes around tags

## v2.3.0 (2023-10-21)

### Feat

- Add continue-on-error input for clean action

## v2.2.0 (2023-10-21)

### Feat

- Introduce clean action

## v2.1.0 (2023-10-21)

### Feat

- Accept image-name input for build-image-docker

## v2.0.0 (2023-10-21)

### BREAKING CHANGE

- You'll need to adjust your branch protection rules
if you depend on the status check name.

### Refactor

- Shorten build-container-image to build

## v1.0.1 (2023-10-21)

### Fix

- Remove condition for build-container-image job

## v1.0.0 (2023-10-21)

Initial version.
