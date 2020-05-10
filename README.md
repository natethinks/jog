# jog

Simple script for zsh users that prints the last few commands you ran in the current directory.

![Gif of Fezzik jogging memory](https://media1.giphy.com/media/5PNM2yFGbUVK8/giphy.gif?cid=ecf05e47a644d0cfbeab72eab8ea67edb714352983ffd82b&rid=giphy.gif)

## Usage

Add this function to your `.zshrc`
```
function zshaddhistory() {
	echo "${1%%$'\n'}|${PWD}   " >> ~/.zsh_history_ext
}
```
This function outputs each command you run and the current directory into a new file called `.zsh_history_ext`.

Download or copy the `jog` script from this repo and place it somewhere in your path. 

There's no way to retroactively store the directory in which a command was run, so this tool will only work from this point forward.

## Todo List
Contributions and feature requests are welcome

- Add bash support
- Automatically truncate `.zsh_history_ext` when `HISTSIZE` is surpassed
