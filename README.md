# docker-setup-action

GitHub Action to run [`docker-setup`](https://github.com/nicholasdille/docker-setup) and install tools from the container ecosystem.

## Inputs

### `version`

Version of `docker-setup` to use. It can be set to any existing version (at least 2.2.49) and defaults to `latest`.

### `path`

Path to install `docker-setup` into. Defaults to `/usr/local/bin`.

### `tools`

Space separated list of tools to install. If this is not empty, the metadata will be updated automatically. Defaults to an empty string.

### `prefix`

Directory under which to install tools. Defaults to an empty string.

### `skip-conflicts`

Skip tools that cause a conflict. Defaults to `true`.

## Outputs

None

## Examples

Install all tools using the latest version of `docker-setup`:

```yaml
    - name: Install
      uses: nicholasdille/docker-setup-action@v1
```

Install only some tools:

```yaml

  - name: Install
    uses: nicholasdille/docker-setup-action@v1
    with:
      only: true
      list: "docker yq"
```

Install using a specific version of `docker-setup`:

```yaml

    - name: Install
      uses: nicholasdille/docker-setup-action@v1
      with:
        version: 1.4.8
```
