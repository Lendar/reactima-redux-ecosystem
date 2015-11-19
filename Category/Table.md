##Category Theory for ES6

### Table of Contents
This is an attempt to recompile [Category Theory for Programmers]() by [Bartosz Milewski](https://twitter.com/BartoszMilewski) in ES6.
Bartosz Milewski work is great, however most of examples are heavily relied on [Haskell](https://www.haskell.org/) - statically typed purely-functional programming language for guys with Ph.D. 

Sub-goal is to find parallels with great [Ramda.js](http://ramdajs.com/) library
```
The primary distinguishing features of Ramda are:
* Ramda emphasizes a purer functional style. Immutability and side-effect free functions are at the heart of its design philosophy. This can help you get the job done with simple, elegant code.
* Ramda functions are automatically curried. This allows you to easily build up new functions from old ones simply by not supplying the final parameters.
* The parameters to Ramda functions are arranged to make it convenient for currying. The data to be operated on is generally supplied last.

The last two points together make it very easy to build functions as sequences of simpler functions, each of which transforms the data and passes it along to the next. Ramda is designed to support this style of coding.
```

#### Part One
* Category: The Essence of Composition
* Types and Functions
* Categories Great and Small
* Kleisli Categories
* Products and Coproducts
* Simple Algebraic Data Types
* Functors
* Functoriality
* Function Types
* Natural Transformations

#### Part Two
* Declarative Programming
* Limits and Colimits
* Free Monoids
* Representable Functors
* The Yoneda Lemma
* Yoneda Embedding

#### Part Three
* It’s All About Morphisms
* Adjunctions
* Monads
* Comonads
* F-Algebras
* Algebras for Monads
* Kan Extensions

