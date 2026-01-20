# gabengar.github.io

## Setup

1. Clone the project
   ```sh
   git clone --recurse-submodules https://github.com/GabenGar/gabengar.github.io.git gabengar-github-io
   cd gabengar-github-io
   git submodule update --init --recursive
   ```

2. Build pages:
   ```sh
   cd todos
   npx turborepo run prune frontend
   cd out
   npm ci
   npm run build-frontend
   ```

The output will be in `./todos/out/apps/frontend/out`.


## Develop

### Set up git configuration

1. Open config at `./.git/config`.

2. Add user section:
   ```ini
   [user]
       name = <user_name>
       email = <user_email>
   ```

3. Add SSH key invocation on push in the `[core]` section:
   ```ini
   [core]
       ...
       sshCommand = ssh -i <ssh_key_path> -F /dev/null
   ```

4. Set the SSH push url on the origin remote:
   ```ini
   [remote "origin"]
       ...
       pushurl = git@github.com:<name>/<repo>.git
   ```

5. Set to check submodule on push:
   ```ini
   [push]
	     recurseSubmodules = check
   ```

6. Open each config in `./.git/modules/**/config` and repeat steps 2 to 4 in related submodules.

### Update the state of remotes

```sh
git submodule update --remote
```

### Fetching

Fetch the latest remotes on all submodules:
```sh
git fetch --all --prune --recurse-submodules=yes
```
