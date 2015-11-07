### Immutable.js related notes
This is an attempt to find some core answers on Immutable.js related hype.
* - [ ]  What makes [Immutable.js](https://facebook.github.io/immutable-js/) is so special?
* - [ ]  [ramda](https://github.com/ramda/ramda) vs [lodash](https://lodash.com/docs#map) Which (fun) iterating library is the best for immutable and functional approach?

> :octocat:: ramda seems iterating really  well over arrays, but not objects and other structures like Immutable.js 

  * :tea: [Put callback first for elegance](http://glebbahmutov.com/blog/put-callback-first-for-elegance/)
  * (fun) [The Philosophy of Ramda](https://github.com/ramda/ramda)
  
> https://github.com/ramda/ramda/issues/695 I am frequently dealing with other kinds of data structures (for example, facebook's immutable data structures). Currently I'm just wrapping up immutable's methods in curryN's to get similar behavior, but it really would be nice to translate the increasing amount of work in this library in other places (for example, immutable does have map, but it doesn't have some of the other funcs, and these just need to be re-written (often times copy-pasting with minimal changes)). I was wondering whether consideration had been given to generalizing these functions, perhaps against JS's iterator spec (https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/The_Iterator_protocol)?  


### Immutable.js links

* [Directed Acyclic Graphs wiki](https://en.wikipedia.org/wiki/Directed_acyclic_graph) 
* [Trie wiki](https://en.wikipedia.org/wiki/Trie) 
* ["Immutable данные в JS приложениях", Дмитрий Кунин, MoscowJS 20](http://www.slideshare.net/moscowjs/immutable-js-moscowjs-20) 
* [Immutable Data Structures and JavaScript](http://jlongster.com/Using-Immutable-Data-Structures-in-JavaScript)

#### Examples
[redux-immutable](https://github.com/gajus/redux-immutable) package provides a single function `combineReducers`, which implements:

* Immutable state.
* [Canonical Reducer Composition](https://github.com/gajus/canonical-reducer-composition).

Refer to https://github.com/gajus/redux-immutable-examples for an example of a Redux app using `redux-immutable`.

* [redux-immutablejs](https://github.com/indexiatech/redux-immutablejs) This library doesn't dictate any specific reducer structure, While `redux-immutable` focusing on [CRC](https://github.com/gajus/canonical-reducer-composition), while this library provides some [conversion middlewares](https://github.com/gajus/redux-immutable/issues/3) from FSA to CCA and vise versa, if you feel like going with _Redux's vanilla_ is the right approach, then consider using our library.

- [ ] Compare with https://github.com/quangbuule/redux-example


### Functional Reactive Alternatives
- [ ] There's always smth else ...
* (fun) [lazy.js](http://danieltao.com/lazy.js/)
* (fun) [bacon.js](https://github.com/baconjs/bacon.js)
* [Circle.js](http://cycle.js.org/) [@andrestaltz](https://twitter.com/andrestaltz)
  * [UNIDIRECTIONAL USER INTERFACE ARCHITECTURES](http://staltz.com/unidirectional-user-interface-architectures.html)
   



