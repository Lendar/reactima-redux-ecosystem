### Immutable.js notes
* [Immutable.js](https://facebook.github.io/immutable-js/) 
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


