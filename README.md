# my-bashrc

![The Fighting Temeraire](https://upload.wikimedia.org/wikipedia/commons/thumb/3/30/The_Fighting_Temeraire%2C_JMW_Turner%2C_National_Gallery.jpg/960px-The_Fighting_Temeraire%2C_JMW_Turner%2C_National_Gallery.jpg)

*"The Fighting Temeraire" (1839) by J.M.W. Turner — [Wikipedia](https://en.wikipedia.org/wiki/The_Fighting_Temeraire)*

**Personal .bashrc for Linux -- Caps Lock is Ctrl, Git in the prompt, and `rm` asks before it destroys.**

## About

A Bash configuration originally used on a NixOS/Linux setup before migrating to macOS and ZSH. It reflects the same keyboard-first philosophy found across the rest of the dotfiles: Caps Lock is remapped to Control (via `setxkbmap`), the prompt shows Git branch and dirty state, and safety nets protect against destructive typos.

This is the predecessor to the [zshrc](https://github.com/pdelfino/zshrc) config, kept here for reference and for anyone who still prefers Bash.

## Key Highlights

- **Caps Lock as Control** -- `setxkbmap -option ctrl:swapcaps` runs on shell startup
- **Git-aware prompt** -- shows current branch and dirty state using `git-prompt.sh`
- **Git tab completion** -- via `git-completion.bash`
- **Safety alias** -- `rm` is aliased to `rm -i` (interactive mode) to prevent accidental deletions
- **Color prompt** -- username in purple, git info in green, directory in blue
- **History management** -- 2,000 lines, duplicates ignored, appended across sessions

## Dependencies

- `git-prompt.sh` and `git-completion.bash` (expected in `~/`)
- A Linux system with X11 (for `setxkbmap`)

## Installation

```bash
git clone git@github.com:pdelfino/my-bashrc.git ~/projects/my-bashrc
ln -sf ~/projects/my-bashrc/.bashrc ~/.bashrc
source ~/.bashrc
```

## Tip

For a safer alternative to `rm -i`, consider [trash-cli](https://github.com/andreafrancia/trash-cli). It moves files to the system trash instead of permanently deleting them -- a much stronger safety net than a confirmation prompt.

## Related

- [zshrc](https://github.com/pdelfino/zshrc) -- The successor ZSH configuration for macOS
- [my-nixos-config](https://github.com/pdelfino/my-nixos-config) -- The NixOS system config that paired with this .bashrc
- [macos-setup](https://github.com/pdelfino/macos-setup) -- The current macOS bootstrap setup

## License

Personal configuration -- use freely.
