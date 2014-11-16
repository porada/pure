# Pure

> Pretty, minimal and fast ZSH prompt

![screenshot](screenshot.png)


## Overview

Most prompts are cluttered, ugly and slow. I wanted something visually pleasing that stayed out of my way.

### Why?

- Comes with the perfect prompt character.
  Author went through the whole Unicode range to find it.
- Shows `git` branch and whether it's dirty (with a `*`).
- Indicates when you have unpushed/unpulled `git` commits with up/down arrows.
- Prompt character turns red if the last command didn't exit with `0`.
- Command execution time will be displayed if it exceeds the set threshold.
- Shows the current path in the title and the current folder and command when a process is running.
- Makes an excellent starting point for your own custom prompt.


## Install

1. Either…
  - Clone this repo
  - add it as a submodule, or
  - just download `pure.zsh`

2. Symlink `pure.zsh` to somewhere in [`$fpath`](http://www.refining-linux.org/archives/46/ZSH-Gem-12-Autoloading-functions/) with the name `prompt_pure_setup`.

#### Example

```sh
$ ln -s "$PWD/pure.zsh" /usr/local/share/zsh/site-functions/prompt_pure_setup
```
*Run `echo $fpath` to see possible locations.*

For a user-specific installation (which would not require escalated privileges), simply add a directory to `$fpath` for that user:

```sh
# .zshenv or .zshrc
fpath=( "$HOME/.zfunctions" $fpath )
```

Then install the theme there:

```sh
$ ln -s "$PWD/pure.zsh" "$HOME/.zfunctions/prompt_pure_setup"
```


## Getting started

Initialize the prompt system (if not so already) and choose `pure`:

```sh
# .zshrc
autoload -U promptinit && promptinit
prompt pure
```


## Options

### `PURE_CMD_MAX_EXEC_TIME`

The max execution time of a process before its run time is shown when it exits. Defaults to `5` seconds.

### `PURE_GIT_PULL`

Set `PURE_GIT_PULL=0` to prevent Pure from checking whether the current Git remote has been updated.

### `PURE_GIT_UNTRACKED_DIRTY`

Set `PURE_GIT_UNTRACKED_DIRTY=0` to not include untracked files in dirtiness check. Only really useful on extremely huge repos like the WebKit repo.

## Example

```sh
# .zshrc

autoload -U promptinit && promptinit

# optionally define some options
PURE_CMD_MAX_EXEC_TIME=10

prompt pure
```


## Tips

[Tomorrow Night Eighties](https://github.com/chriskempson/tomorrow-theme) theme with the [Droid Sans Mono](http://www.google.com/webfonts/specimen/Droid+Sans+Mono) font (15pt) is a beautiful combination, as seen in the screenshot above. Just make sure you have anti-aliasing enabled in your Terminal.

To have commands colorized as seen in the screenshot install [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting).


## License

MIT © [Sindre Sorhus](http://sindresorhus.com)
