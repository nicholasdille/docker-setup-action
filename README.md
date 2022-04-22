# docker-setup-action

GitHub Action to run [`docker-setup`](https://github.com/nicholasdille/docker-setup) and install tools from the container ecosystem.

## Inputs

### `version`

Version of `docker-setup` to use. It can be set to any existing version (e.g. 1.4.8) and defaults to `latest`.

### `check`

Whether to check tools after installation. It defaults to `false`.

### `only`

Whether to install tools provided by `list`. It defaults to `false`. Mutually exclusive with `tags`.

### `tags`

Whether to install tools selected by tags provided in `list`. It defaults to `false`. Mutually exclusive with `only`.

### `list`

Tool names or tags names to install. Requires `only` or `tags`. Empty by default.

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
