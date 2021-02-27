# paths

`paths` is a command line tool for specifying the initial `$PATH` environment variable.
It is similar to `path_helper` except that it actually makes sense.
It is written in pure Bash and expects a valid Bash at `/bin/bash`.

## How it works

`paths` reads paths from `/etc/paths.d/*` and `/etc/paths` and creates a PATH variable from it delimited by colons.
It reads the files in alphabetical order, always reading `/etc/paths` last.
It reads the lines in the file by line order.

## Example

```
/etc/paths:
    /usr/bin
    /bin
/etc/paths.d/10-go:
    /opt/go/bin
/etc/paths.d/20-homebrew:
    /opt/homebrew/bin
```

```
/opt/go/bin:/opt/homebrew/bin:/usr/bin:/bin
```

## License

This project is licensed under the GNU General Public License v3.0.
