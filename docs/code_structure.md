#Code Structure

After executing the comand `stack new my-project` command, you will see some folders and files:

```
.
├── app/
│   └── Main.hs
├── src/
│   └── Lib.hs
├── test/
│  └── Spec.hs
├── LICENSE
├── Setup.hs
├── my-project.cabal
└── stack.yaml

```

Lets break down each one:

* `app/` - In this folder we can add all source files that compose our executable.
* `src/` - In this folder we can add all source files that compose the core functionality of our app.
* `test/` - In this folder we can add files related to test our app.
* `LICENCE` - This is a text file with a legal note, it has no computational effects in our code.
* `Setup.hs` -  This file is a component of the Cabal build system which stack uses.
* `my-project.cabal` -  Stack is built on top of the Cabal build system. In Cabal, we have individual packages, each of which contains a single .cabal file. 
* `stack.yaml` -  That file contains a reference, called a resolver, to the snapshot which your package will be built against.
