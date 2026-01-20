# gabengar.github.io

## Develop

### Clone the project

```sh
git clone --recurse-submodules https://github.com/GabenGar/gabengar.github.io.git
git submodule update --init --recursive
```

### Update the state of remotes

```sh
git submodule update --remote
```

### Pushing

Fail if any of the submodules aren't pushed:
```sh
git push --recurse-submodules=check
```

Set this as default behaviour:
```sh
git config push.recurseSubmodules check
```

Push submodules first before pushing the main repo:
```sh
git push --recurse-submodules=on-demand
```

Set this as default behaviour:
```sh
git config push.recurseSubmodules on-demand
```

After pull:
```sh
git submodule update --init --recursive
```

### Set up push url for a submodule

```sh
git config submodule.todos.pushurl <PRIVATE_URL>
```
