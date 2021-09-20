# Syd's rules for sustainable Haskell


* Make the simplest thing you can get away with.
* Don't make things more general than you need to.
* Don't make a system distributed if that's not a hard requirement.
* Use sqlite if you can get away with not having more than one machine.
* Use postgres if you cannot get away with having only one machine.
* Solve the problem you have, not the problem you hope to have.
* Write tests first. If you can't do that, you've probably made things too complex.
* Ban [dangerous functions](https://github.com/NorfairKing/haskell-dangerous-functions). Think twice before introducing exceptions.
* Know about [WATs](https://github.com/NorfairKing/haskell-WAT)
* Remove every instance that you don't use.
* Before writing an instance, write a function. Then reconsider whether you still need an instance. (You probably don't.)
* Don't write an instance if you can't use it to write generic code.
* If your instance is not law-abiding, remove it.
* Write json instances manually, and have roundtrip tests.
* Don't use lenses. You don't need them.
