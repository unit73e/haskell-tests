# Glasskow Haskell Compiler

The Glasskow Haskell Compiler (GHC) is the current *de facto* standard
implementation of Haskell.

GHC has three main components:

* `ghc` is a compiler that generates optimized native code
* `ghci` is an interactive interpreter and debugger
* `runghc` is a program for running Haskell programs as scripts without
  compiling them first

Each component will be described in the next sections, starting with the
interpreter.

## Interpreter

The GHC interpreter is...

Running `ghci` opens the interpreter:

    $ ghci
    GHCi, version 7.8.4: http://www.haskell.org/ghc/  :? for help
    Loading package ghc-prim ... linking ... done.
    Loading package integer-gmp ... linking ... done.
    Loading package base ... linking ... done.
    Prelude> 

By default the prompt is defined as `%s >` where `%s` is replaced by the names
of the modules currently in scope. The `Prelude` is a module that implements a
set of useful libraries. The `Prelude` is always implicitly available, meaning
the types, values and functions it defines can be used without any additional
steps.

To load a new module run the `:module +` command:

    Prelude> :module +Data.Ratio
    Prelude Data.Ratio> 

As you can see both `Predule` and `Data.Ratio` are now in scope. If many modules
are in scope, the default prompt can become quite large and cumbersome. To change
the prompt to something else run the `:set prompt` command:

    Prelude Data.Ratio> :set prompt "λ> "
    λ> 


