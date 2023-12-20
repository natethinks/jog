# jog

Print the last 10 commands you ran in the current directory

![Gif of Fezzik jogging memory](https://media1.giphy.com/media/5PNM2yFGbUVK8/giphy.gif?cid=ecf05e47a644d0cfbeab72eab8ea67edb714352983ffd82b&rid=giphy.gif)

## Usage

1. Add this function to your `.zshrc`

```
function zshaddhistory() {
  if [[ "${1}" != ${~HISTORY_IGNORE} ]]; then
	echo "${1%%$'\n'}⋮${PWD}   " >> ~/.zsh_history_ext
  fi
}
```

2. Download or copy the `jog` script from this repo and place it somewhere in your `$PATH`.

3. Run `touch ~/.zsh_history_ext ; chmod 600 ~/.zsh_history_ext` to ensure that only you can read and write your history.

4. Restart your current terminal sessions for changes to take effect. `exec $SHELL`

5. Use `jog` whenever you find yourself lost and confused.

It's not possible to retroactively store the directory in which a command was run, so **this tool will only work from this point forward.**

## Todo List

Contributions and feature requests are welcome

- Add support for other shells: bash, fish.
- Automatically truncate `.zsh_history_ext` when `HISTSIZE` is surpassed
