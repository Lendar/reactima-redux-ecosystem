##Category Theory for ES6

### Table of Contents
This is an attempt to recompile and interate over thoughts and ideas from [Category Theory for Programmers](http://bartoszmilewski.com/2014/10/28/category-theory-for-programmers-the-preface/) by [Bartosz Milewski](https://twitter.com/BartoszMilewski) into ES6 examples.
Bartosz Milewski work is great, however most of examples are heavily relied on [Haskell](https://www.haskell.org/) ([tryhaskell.org](https://tryhaskell.org/)) - statically typed purely-functional programming language for guys with Ph.D. ... and ... C++. This is not for humans who needs quick results and under heavy pressure from business. 

Sub-goal is to find parallels with great [Ramda.js](http://ramdajs.com/) library.
```
Ramda's distinguishing features are:
* Ramda emphasizes a purer functional style. 
  Immutability and side-effect free functions are at the heart of its design philosophy. 
* Ramda functions are automatically curried. 
* The parameters to Ramda functions are arranged to make it convenient for currying. 
  The data to be operated on is generally supplied last.
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

### Terms
Transducers are composable algorithmic transformations. They are independent from the context of their input and output sources and specify only the essence of the transformation in terms of an individual element. Because transducers are decoupled from input or output sources, they can be used in many different processes - collections, streams, channels, observables, etc. Transducers compose directly, without awareness of input or creation of intermediate aggregates.



