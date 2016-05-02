#New Project & Adding dependencies
After installing [stack](http://http://docs.haskellstack.org/) in my environment the first thing I've tried was to create a new project. Pretty easy thing, just see this instructions on the official page:

```
stack new my-project
cd my-project
stack setup
stack build
stack exec my-project-exe
```

To me, this run smothly. But when I tryied to **add a dependency**. I read this line of the [User Guide](http://docs.haskellstack.org/en/stable/GUIDE/) as follows:

```
To tell stack to use [dependency], you need to add it to 
your .cabal file — specifically in your build-depends section.
```

After that, used `stack build` and stack take care of incluiding it in my project. Well, when trying to `import` the dependecy the console was pointing out that there was a missing dependecy. Holy moly... name checked twice, added to stack.yaml, removed from .cabal, removed from stack.yaml, trying to install from console (not sure if it's even posible). Googled for a while, nothing worked so I return to de Guide an read it again.

It turns out that the .cabal file has three `build-depends` options, one for source, other for the executable and other for test (AKA `/src`, `/app` `/test` folders) and it clearly says that you should add it to the library build-depends section this way:

```
library
  hs-source-dirs:      src
  exposed-modules:     Lib
  build-depends:       base >= 4.7 && < 5
                       -- This next line is the new one
                     , [dependency]
  default-language:    Haskell2010
```

Where instead of `[dependency]` goes the name of your dependency, lets say `text`. After that, I was able to play with my recently imported modules. Hope this help anyone that runs with the same issue.
