# Plugin Linter Buildkite Plugin [![Build status](https://badge.buildkite.com/044827c84a7a6aa9d9b80ff3f1f7285189607fe0c39e17e8d6.svg?branch=master)](https://buildkite.com/buildkite/plugins-plugin-linter)

A [Buildkite plugin](https://buildkite.com/docs/agent/v3/plugins) to lint your Buildkite plugins 😱

For a full list of features see the [Buildkite Plugin Linter cli tool documentation](https://github.com/buildkite-plugins/buildkite-plugin-linter).

## Usage

```yaml
steps:
  - label: ":sparkles: Lint"
    plugins:
      - plugin-linter#v3.1.0:
          id: my-org/my-plugin
```

Note: this will pull the latest version of the Plugin Linter each time it is run.

If you want to run it locally on a command line, see the [Buildkite Plugin Linter cli tool documentation](https://github.com/buildkite-plugins/buildkite-plugin-linter).

## Configuration

### `id`

The id of the plugin (e.g. `my-org/my-plugin`)

### `image-version`

The docker tag of the `buildkite/plugin-linter` image to use. Default is `2.0.2`

### `readme` (optional)

The filename of the plugin’s readme. Default is `README.md`

## Developing

To run testing, shellchecks and plugin linting use use `bk run` with the [Buildkite CLI](https://github.com/buildkite/cli).

```bash
bk run
```

Or if you want to run just the tests, you can use the docker [Plugin Tester](https://github.com/buildkite-plugins/buildkite-plugin-tester):

```bash
docker run --rm -ti -v "${PWD}":/plugin buildkite/plugin-tester:latest
```

## License

MIT (see [LICENSE](LICENSE))
