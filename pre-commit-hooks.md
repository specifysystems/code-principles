# Pre-commit hooks

Pre-commit hooks are a crucial step of the development process.

Each hook checks the code for a specific issue and prevents commit
if issues were found.

This helps enforce quality standards and prevents accidentally mishaps.

## Configuration

Install [pre-commit.com](https://pre-commit.com/#install)

Then run the following line to set up a pre-commit hook:

```sh
pre-commit install
```

And this to update hooks to the newest version:

```sh
pre-commit autoupdate
```

Finally, create a `.pre-commit-config.yaml` file and add configure
some hooks. Hooks used by existing projects at specify are described
in the `./language` folder.

[Example hooks config
file](https://github.com/specify/specify7/blob/production/.pre-commit-config.yaml)

## Running the hooks

Whenever you try to commit, hooks defined in the config file would run
and check staged files.

Alternatively, hooks can be triggered manually:

```sh
pre-commit run
```

Hooks can be run on specific files only

```sh
pre-commit run --files *.ts
```

Or, they can be run on all the files in the repository (this should be done
after adding new hooks to the repository):

```sh
pre-commit run --all-files
```

Finally, you can disable some hooks by listing them in the `SKIP` environment
variable:

```sh
# Don't make a habit out of this
SKIP=flake8,black git commit
```

## See Also

[Syncing pre-commit hooks across
repositories](https://github.com/maxxxxxdlp/pre-commit-tools#syncing-global-and-local-pre-commit-files)

[Keeping pre-commit hooks
up-to-date](https://github.com/maxxxxxdlp/pre-commit-tools#updating-global-hooks-config-file)