#dot

`dot` is a simple shell script to help me keep my dotfiles in sync across
machines.

The dotfiles live in a separate `git` repository that is managed via `dot`.
I've put this together as an replacement to `vcsh` (which probably is what you
should be using instead) because I was confused with how to use submodules.
With `dot` I add various submodules via `dot submodule add REPO`. When I work
on the submodules itself I do not use the `dot` wrapper directly, but usual
`git` instead. After comitting in the submodule, I add and commit via `dot`.
So far I've had no issues.

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

**`dot clear`**
Remove conflicting files.

**`dot unclear`**
Reinstate the latest backup created by `dot clear`.

**`dot initialize`**
Clone and initialize the dotfile repository.

**`dot shell`**
Enter a shell with `GIT_DIR` and `GIT_WORK_TREE` set.

Most of the time you'll be using `dot` like `git` (e.g. edit some file, run `dot
add`, `dot commit -m"..."` and `dot push`).

## Dependencies

* `zsh`
