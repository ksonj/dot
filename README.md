#dot

`dot` is a simple shell script to help me keep my dotfiles in sync across
machines.

The dotfiles live in a separate `git` repository that is managed via `dot`.
I've put this together as an replacement to `vcsh` (which probably is what you
should be using instead) for reasons I do not quite remember.

## Installation

Clone this repository

    git clone https://github.com/ksonj/dot.git

Copy `dotrc` to `~/.dotrc` and edit it to match your setup (i.e. include the
location to your dotfile repository).

Then run `dot initalize` and you're good to go!

## well...
..., probably not quite: some of the files that are to be downloaded will most
likely already exist in your `$HOME`. In that case either clean up yourself,
i.e. move (and backup) your files OR run

    dot clear

to remove all conflicting files (a backup is created). Then run `dot initialize`
again.

## Usage

`dot` provides 4 special commands, other than that it is just an alias to `git`
with `GIT_DIR` and `GIT_WORK_TREE` set:

### `dot clear`
Remove conflicting files.

### `dot unclear`
Reinstates the latest backup created by `dot clear`.

### `dot initialize`
Clone and initialize the dotfile repository.

### `dot shell`
Enter a shell with `GIT_DIR` and `GIT_WORK_TREE` set.
