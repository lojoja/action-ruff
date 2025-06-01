# action-ruff

A composite action lints and checks file formattings with [Ruff](https://docs.astral.sh/ruff/).

This repository is not meant to be referenced in third-party workflows; please fork the repository if you would like to use it in your project.

## Inputs

| Name              | Description                                       | Required | Default |
| ----------------- | ------------------------------------------------- | :------: | ------- |
| cache             | Whether to cache project dependencies.            |          | "true"  |
| command           | The command to execute ("check" or "format")      |    ✅    |         |
| package_manager   | The package manager to use ("poetry" or "uv").    |          | "uv"    |
| python_version    | The python version to use in SemVer range syntax. |          | "3.13"  |
| working_directory | The working directory for the action.             |          | "."     |

## Examples

### Ruff Lint

```
jobs:
  ruff:
    runs-on: ubuntu-latest
    steps:
      - uses: lojoja/action-ruff@main
        with:
          cache: "true"
          command: check
          package_manager: uv
          python_version: "3.13"
```

### Ruff Format

```
jobs:
  ruff:
    runs-on: ubuntu-latest
    steps:
      - uses: lojoja/action-ruff@main
        with:
          cache: "true"
          command: format
          package_manager: uv
          python_version: "3.13"
```

## License

action-ruff is released under the [MIT License](./LICENSE)
