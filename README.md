# check-github-repository-update

## Description

An action to check a GitHub repository's update.

## Required input

1. repository: GitHub Repository path.
1. ref: Ref of GitHub Repository.
1. working_directory: Working directory.
1. command_output: Path of the git log output file.
1. cache_key_prefix: Key prefix for cache of the git log output file.

## Output

1. is_updated: If the repository is updated, true.

## Example

```yaml
jobs:
  check:
    runs-on: ubuntu-latest
    steps:
      - uses: smilerobotics/actions-check-github-repository-update@v1
        id: check
        with:
          repository: smilerobotics/actions-check-github-repository-update
          ref: main
          working_directory: .
          command_output: ~/is_updated
          cache_key_prefix: "is-updated"
      - run: echo ${{ steps.check.outputs.is_updated }}
        shell: bash
```
