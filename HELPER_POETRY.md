
## Global Options

| Option                     | Description                                                                 |
|----------------------------|-----------------------------------------------------------------------------|
| `-h, --help`               | Display help.                                                               |
| `-q, --quiet`              | Do not output any message.                                                  |
| `-V, --version`            | Display the application version.                                            |
| `--ansi`                   | Force ANSI output.                                                          |
| `--no-ansi`                | Disable ANSI output.                                                        |
| `-n, --no-interaction`     | Do not ask any interactive question.                                        |
| `--no-plugins`             | Disable plugins.                                                            |
| `--no-cache`               | Disable Poetry source caches.                                               |
| `-P, --project=PROJECT`    | Specify another path as the project root.                                  |
| `-C, --directory=DIR`      | Working directory for the command (defaults to current directory).          |
| `-v`, `-vv`, `-vvv`        | Increase verbosity: 1 for normal, 2 for verbose, 3 for debug output.        |

---

## Main Commands

| Command         | Description                                                   |
|-----------------|---------------------------------------------------------------|
| `about`         | Show information about Poetry.                                |
| `add`           | Add a new dependency to `pyproject.toml` and install it.     |
| `build`         | Build a package (tarball and wheel by default).               |
| `check`         | Validate `pyproject.toml` and `poetry.lock` consistency.      |
| `config`        | Manage configuration settings.                                |
| `help`          | Display help for a command.                                   |
| `init`          | Create a basic `pyproject.toml` in the current directory.     |
| `install`       | Install project dependencies.                                 |
| `list`          | List available commands.                                      |
| `lock`          | Lock project dependencies.                                    |
| `new`           | Create a new Python project at `<path>`.                      |
| `publish`       | Publish package to a remote repository.                       |
| `remove`        | Remove a dependency from the project.                         |
| `run`           | Run a command within the Poetry environment.                  |
| `search`        | Search for packages on remote repositories.                   |
| `show`          | Show information about installed packages.                    |
| `sync`          | Sync the environment with the lockfile.                       |
| `update`        | Update dependencies per `pyproject.toml`.                     |
| `version`       | Show or bump the project version.                             |

---

## Cache Commands

| Command         | Description                          |
|-----------------|------------------------------------|
| `cache clear`   | Clear a Poetry cache by name.       |
| `cache list`    | List Poetry's caches.                |

---

## Debug Commands

| Command          | Description                                           |
|------------------|-------------------------------------------------------|
| `debug info`     | Show environment and Poetry debug information.        |
| `debug resolve`  | Debug dependency resolution.                           |
| `debug tags`     | Show compatible tags for the active Python environment.|

---

## Env Commands

| Command           | Description                                                      |
|-------------------|------------------------------------------------------------------|
| `env activate`    | Print the command to activate the virtual environment.           |
| `env info`        | Show information about the current environment.                  |
| `env list`        | List all virtual environments for the project.                   |
| `env remove`      | Remove one of the project's environments.                        |
| `env use`         | Activate or create a new virtualenv for the current project.     |

---

## Python Commands (Experimental)

| Command           | Description                                                              |
|-------------------|--------------------------------------------------------------------------|
| `python install`  | Install the specified Python version (from standalone builds).           |
| `python list`     | Show Python versions available for this environment.                     |
| `python remove`   | Remove the specified Python version (if managed by Poetry).              |

---

## Self Commands

| Command               | Description                                                           |
|-----------------------|-----------------------------------------------------------------------|
| `self add`            | Add packages to Poetry’s runtime environment.                         |
| `self install`        | Install locked packages required by the Poetry installation.          |
| `self lock`           | Lock the Poetry installation’s system requirements.                   |
| `self remove`         | Remove additional packages from Poetry’s runtime environment.         |
| `self show`           | Show packages installed in Poetry’s runtime environment.              |
| `self show plugins`   | Show information about currently installed plugins.                   |
| `self sync`           | Sync Poetry’s environment with the locked packages.                   |
| `self update`         | Update Poetry to the latest version.                                  |

---

## Source Commands

| Command          | Description                                               |
|------------------|-----------------------------------------------------------|
| `source add`     | Add source configuration to the project.                  |
| `source remove`  | Remove a configured source from the project.              |
| `source show`    | Show information about configured sources.                |
