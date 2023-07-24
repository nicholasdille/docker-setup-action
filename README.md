# docker-setup-action

GitHub Action to run [`docker-setup`](https://github.com/nicholasdille/docker-setup) and install tools from the container ecosystem.

## Deprecation notice

`docker-setup` is in the process of being renamed to [`uniget`](https://github.com/uniget-org/uniget):

| Component     | Migration status | Support status | Notes |
| ------------- | ---------------- | ----- | --- |
| CLI           | Completed        | `docker-setup` will only receive security updates | `uniget` is a drop-in replacement with data migration | - |
| GitHub Action | Completed        | `docker-setup-action` will only receive security updates | `uniget-action` is a dop-in replacement using `uniget` |

For more information, please refer to [`docker-setup`](https://github.com/nicholasdille/docker-setup).

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
