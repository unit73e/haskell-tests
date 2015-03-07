# Haskell

Haskell is standardized, general purpose purely functional programming
language, with non strict evaluation and strong static typing.

Haskell is standardized because a specification exists which defines how the
language and libraries should be implemented. The current standard is the
Haskell 2010 standard. There are many implementations of Haskell, however
Glaskow Haskell Compiler (GHC) currently represents *de facto* standard
implementation.

A general purpose programming language is a programming language that has been
designed for writing software in a wide variety of application domains. In
contrast, a domain specific language is designed to be used within a specific
application domain (e.g., HTML for web pages, Unix shell scripts for data
organization). Haskell has been designed to write any kind of software, not
just one particular application domain.

TODO

## Glasskow Haskell Compiler

GHC has three main components:

* `ghc` is a compiler that generates optimized native code
* `ghci` is an interactive interpreter and debugger
* `runghc` is a program for running Haskell programs as scripts without
  compiling them first

We will describe each component in the next sections.

### Interpreter

Running `ghci` opens the interpreter:

    $ ghci
    GHCi, version 7.8.4: http://www.haskell.org/ghc/  :? for help
    Loading package ghc-prim ... linking ... done.
    Loading package integer-gmp ... linking ... done.
    Loading package base ... linking ... done.
    Prelude> 

By default the prompt is defined as `%s >` where `%s` is replaced by the names
of the modules currently in scope. The `Prelude` a module that implements a set
of useful libraries and the first module to be loaded in every Haskell program.
The `Prelude` is always implicitly available, meaning the types, values and
functions it defines can be used without any additional steps.

To load a new module run the `:module +` command:

    Prelude> :module +Data.Ratio
    Prelude Data.Ratio> 

As you can see both `Predule` and `Data.Ratio` are now in scope. The default
prompt may get big enough to fill a whole line, becoming quite cumbersome. To
change the prompt to something else run the `:set prompt` command:

    Prelude Data.Ratio> :set prompt "ghci> "
    ghci> 

This is the prompt we will be using from here on for simplicity and
consistency.

