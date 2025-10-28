# Rbenv - Docker mod for code-server

This mod adds [rbenv](https://github.com/rbenv/rbenv) to code-server, to be installed/updated during container start.

rbenv is a version manager tool for the Ruby programming language on Unix-like systems. It is useful for switching between multiple Ruby versions on the same machine and for ensuring that each project you are working on always runs on the correct Ruby version.

In code-server docker arguments, set an environment variable `DOCKER_MODS=somewatson/mods:code-server-rbenv-sw`

If adding multiple mods, enter them in an array separated by `|`, such as `DOCKER_MODS=somewatson/mods:code-server-rbenv-sw|linuxserver/mods:openssh-server-mod2`

### Shell completions

This mod includes adding [shell completions](https://github.com/rbenv/rbenv?tab=readme-ov-file#shell-completions) for `rbenv` in `bash` and `zsh`.

The zsh completion script ships with the project, but needs to be added to FPATH in zsh before it can be discovered by the shell. So, the mod will automatically detect and update the `~/.zshrc` file:

```
FPATH=~/.rbenv/completions:"$FPATH"
autoload -U compinit
compinit
```
