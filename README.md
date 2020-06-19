# grr
grr: git run root - run a file in the git repo root, with tab completion

# Installation and Setup

## Dependencies

The script needs `git` and `bash`

## Installation

```console
  $ cp grr ${HOME}/tools/bin
  $ chmod a+x ${HOME}/tools/bin
```

## Setup Tab Completion

Add the following to your `.bash_profile`

For bash-3.2 (OSX):

```bash
if [[ -f ${HOME}/tools/bin/grr ]]; then
    source /dev/stdin <<<"$(cat <(${HOME}/tools/bin/grr --bash-complete))"
fi
```

For a newer bash:

```bash
source <(${HOME}/tools/bin/grr --bash-complete)
```


# Usage

Change directory into some deep directory of a git repo.  Type `grr` then hit
`<TAB>` to get a list of executable files and directories in the git repo root.
Pick a command to run, then tab completion reverts to normal argument
completion.

```console
 $ cd git-project
 $ ls
 src/    script.sh    tools/
 $ ls tools
 tool1
 $ cd src/some/sub/directory
 $ grr s<TAB>
 script.sh
 $ grr script.sh f<TAB>
 file1.c file2.c
 $ grr script.sh file1.sh
 git-project/script.sh file1.c
 ...
 $ grr tools/<TAB>
 tool1
 $ grr tools/tool1 *.c
 git-projoect/tools/tool1 file1.c file2.c
 ...
```


 
