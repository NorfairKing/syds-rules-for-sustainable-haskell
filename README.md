# Syd's rules for sustainable Haskell


## General Tips

* Make the simplest thing you can get away with.
* Don't make things more general than you need to.
* Don't make a system distributed if that's not a hard requirement.
* Solve the problem you have, not the problem you hope to have.

## Haskell-specific

* Write tests first. If you can't do that, you've probably made things too complex.
* Choose an automated linter and enforce its use.
* Ban [dangerous functions](https://github.com/NorfairKing/haskell-dangerous-functions). Think twice before introducing exceptions.
* Know about [WATs](https://github.com/NorfairKing/haskell-WAT)
* Choose an automated formatter, don't argue about which one, and enforce its use.
* Remove every instance that you don't use.
* Before writing an instance, write a function. Then reconsider whether you still need an instance. (You probably don't.)
* Don't write an instance if you can't use it to write generic code.
* If your instance is not law-abiding, remove it.
* Have roundtrip tests for any serialisation.
* Have golden tests for any external output you produce. (That means "for every `ToJSON` instance" as well.)
* Write JSON instances manually until you have both roundtrip tests and golden tests.
* Don't use lenses. You don't need them.
* Use prefix naming: `data Thing = { thingField :: FieldType }`
* Use as few languages extensions as you can get away with.
* Don't try to break the laws of physics.
* Don't try to prove "false".
* Don't use any effect systems. Use `IO` or a `ReaderT` with a fixed `Env` over `IO`. No parametric environment and no parametric monad.
* Never implement a custom Show and/or Read instance. If you want an instance, derive it.
* Use monomorphic functions where possible.

## Choosing a database

* Use sqlite if you can get away with using a single machine.
* Use postgres if you cannot get away with having only one machine.
* Stay the hell away from NoSQL databases like MongoDB and CouchDB
