# lstn-gh-action
version: 0.0.1 (pre-release)

> Monitor and control the behavior of dependencies


## Usage

See [action.yml](action.yml).

### Basic

```yaml
steps:
  - uses: listendev/action@v1
```

### Workflows

#### To scan a project

```yaml
steps:
  - uses: garnet-org/lstn-gh-action@0.0.1
    with:
      # The Github API token.
      # Defaults to ${{ github.token }}
      token: "..."
      # The working directory relative to the root one.
      # Defaults to the root directory.
      workdir: "."
      # The lstn command to execute
      # Defaults to 'scan'
      lstn-command: 'scan'

```

#### To scan and project and enforce policy

Uses `rules.yml` in the root directory.

```yaml

steps:
  - uses: garnet-org/lstn-gh-action@0.0.1
    with:
      # The Github API token.
      # Defaults to ${{ github.token }}
      token: "..."
      # The working directory relative to the root one.
      # Defaults to the root directory.
      workdir: "."
      # The lstn command to execute
      # Defaults to 'scan'
      lstn-command: 'scan'
          apply-policy: true
          rules-file: 'rules.yml'
          rule-name: 'ignore_priority_medium'
```
