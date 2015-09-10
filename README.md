#godef
Godef prints the source location of definitions in Go programs.

Download:
```shell
go get github.com/npat-efault/godef
```

This is Roger Peppe's "godef" tool. The original code can be found at:

  https://github.com/rogpeppe/godef

THERE IS NO LONGER ANY REASON TO USE THIS. USE THE ORIGINAL POINTED ABOVE
INSTEAD.

All I did was to move it here (and rewrite some import paths) in order
to be able to "go get" it, without pulling a boat-load of unneeded
clutter (something that happens when you try to get it from Roger's
repository). THIS IS NO LONGER THE CASE.

I also removed the Acme editor support (-acme flag) in order to reduce
its dependencies (and since I don't use Acme).

godef is used by Emacs go-mode. See here for details:

  http://dominik.honnef.co/posts/2013/03/writing_go_in_emacs/ 

* * *

Godef prints the source location of definitions in Go programs.

Usage:

```
godef [-t] [-a] [-A] [-o offset] [-i] [-f file] [expr]
```

File specifies the source file in which to evaluate expr.
Expr must be an identifier or a Go expression
terminated with a field selector.

If expr is not given, then offset specifies a location
within file, which should be within, or adjacent to
an identifier or field selector.

If the -t flag is given, the type of the expression will
also be printed. The -a flag causes all the public
members (fields and methods) of the expression,
and their location, to be printed also; the -A flag
prints private members too.

If the -i flag is specified, the source is read
from standard input, although file must still
be specified so that other files in the same source
package may be found.

Example:

```
$ cd $GOROOT
$ godef -f src/pkg/xml/read.go 'NewParser().Skip'
src/pkg/xml/read.go:384:18
$
```

