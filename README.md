gitignore
=========

This is a hacked together ruby script that pulls profiles from GitHub's gitignore repository, combines them
together into a single file, sorts them, and finally removes duplicate lines and comments.

The script is additive to the existing .gitignore file which means you can:

    gitignore Eclipse
    gitignore Scala

... and that will build a `.gitignore` file that contains the union of those two profiles. Though you can just
as easily issue:

    gitignore Eclipse Scala

to accomplish the same thing.

The script automatically falls back from language profiles to global profiles so:

    gitignore Global/Eclipse

is the same as

    gitignore Eclipse

(But it makes two HTTP requests to figure that out.)

Installation
============

gitignore requires Ruby with no additional gems. It has been tested on 1.9.3 and
should work with 1.8.7. To install symlink the gitignore script somewhere in your
`$PATH`:

    git clone git://github.com/cfeduke/gitignore.git
    cd gitignore
    ln -s `pwd`/gitignore ~/bin/gitignore

Or (in the directory where you want to clone the repo, e.g., `~/Projects`):

    TODO

This simple installation assumes you have a `~/bin` and its in your `$PATH`.

Usage
=====

    usage: gitignore [option] args
    options:
      -f, --file:       specify output filename (default: ".gitignore")
      -v, --verbose:    verbose output 
      -h, --help:       usage information
      --version:        version information
    args:
      .gitignore profile names (e.g., Eclipse, Java, Scala, etc.)

    example:
      gitignore Eclipse Scala vim SBT

    
