# parse_quick_parameters.sh-
Provide a documentation string to get named function parameters. Fork of msknapp's. Similar to docopt


## Installation

Just copy the file or use package managers.

### Use bkpg

Get [bpkg](https://www.bpkg.sh/) and then run:
```bash
bpkg install parse_quick_parameters
```


## Usage

```bash
#!/usr/bin/env bash
source dependencies/parse_quick_parameters/parse_quick_parameters.sh

function do_something_quick {
    parse_quick_parameters "my_file=-f|--file,bool:run=-r|--run,name=-n|--name" "$@" || return 0
    echo "my file is: $my_file"
    echo "my name is: $name"
    echo "run is: $run"
}

do_something_quick --name name --run --file file
do_something_quick "file" "name" --run
```



## Notes

Shellcheck doesn't understand the pattern and will raise [SC2154](https://github.com/koalaman/shellcheck/wiki/SC2154)

## Alternatives

- [getopts](https://en.wikipedia.org/wiki/Getopts) Builtin bash command
- [docopts](https://github.com/docopt/docopts) Shell version of docopts
- [argparse-bash](https://github.com/nhoffman/argparse-bash) Use python's argparse in bash

## Contributing

Use make file. `bats` tests assume bats was installed with npm. 

## Credits

- [msknapp](https://github.com/msknapp/maintainable-bash/blob/master/1_init/3.1_parameters/shortcut.sh#L3)

