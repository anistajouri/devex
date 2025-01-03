# nix


## Nix-shell


nix-shell is a command that allows you to enter a shell with the dependencies specified in a `shell.nix` file. This is useful for building projects that have dependencies specified in a `shell.nix` file.


## Example

This example shows how to use the `nix-shell` command to build a project with github actions.

```shell
nix-shell --command "make build"
```


```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Set up Nix
        uses: cachix/install-nix-action@v2
      - name: Enter Nix Shell and Build
        run: |
          nix-shell --command "make build"
```