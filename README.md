# lstn Policy
version: 0.0.2 (pre-release)

> Enforce rule-based policies to control the behavior of your dependencies using listen.dev


## Usage

See [action.yml](action.yml).

### Basic

```yaml
steps:
  - uses: garnet-org/lstn-policy@v0.0.3
```

### Workflows

#### To scan and project and enforce policy

Uses `rules.yml` in the root directory.

```yaml

steps:
  - uses: garnet-org/lstn-policy@v0.0.3
    with:
      # The working directory relative to the root one.
      # Defaults to the root directory.
      workdir: "."
      # The lstn command to execute
      # Defaults to 'scan'
      lstn-command: 'scan'
      # The option to apply policy
      # Default is true
      apply-policy: true
      # The rules file to use
      # Defaults to './rules.yml'
      rules-file: 'rules.yml'
      # The name of the rule to enforce from rules.yml
      # Defaults to 'ignore_priority_medium'
      rule-name: 'ignore_priority_medium'
```
See [docs](https://docs.listen.dev/lstn-github-action/policies) for a detailed guide rules and policy enforcement. 
