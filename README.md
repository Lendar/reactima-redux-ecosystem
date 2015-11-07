[:game_die:Play with JS/ES6/ES2015!] (JS.md) or [Dev/Sys/OOOPS ](DEVOPS.md) or [TopSmth 3% screening](Notes/TopSmth.md) 
# Hand-picked Redux Ecosystem

Redux - Predictable state container for JavaScript apps which makes you forget about all other frameworks, tools, ecosystems or even coming [WebAssembly] ( https://medium.com/javascript-scene/what-is-webassembly-the-dawn-of-a-new-era-61256ec5a8f6#.1x0ooowqn). Makes you believe that you are in control on apps state and data flow.

* Redux Mafia: [Dan Abramov](https://github.com/gaearon), [React Europe](https://www.react-europe.org/), [Rackt](https://github.com/orgs/rackt/people)
* [Redux Github](https://github.com/rackt/redux)
* [Documentation of Redux](http://rackt.github.io/redux)

### PACKAGE.JSON
* [React.js](http://facebook.github.io/react)
* [react-redux - React bindings for Redux](https://github.com/rackt/react-redux)
* [redux-router - Redux bindings for React Router – keep your router state inside your Redux store](https://github.com/rackt/redux-router)
* [superagent](https://github.com/visionmedia/superagent) for isomorphic calls to APIs
* [Immutable.js](https://facebook.github.io/immutable-js/) READ MORE [Notes/Immutable.md](Notes/Immutable.md)
* - [ ] Which (fun) data structures and library is the best? [ramda](https://github.com/ramda/ramda) vs [lodash](https://lodash.com/docs#map) 

> :octocat:: ramda seems iterating really  well over arrays, but not objects and other structures like Immutable.js 

  * :tea: [Put callback first for elegance](http://glebbahmutov.com/blog/put-callback-first-for-elegance/)
  * (fun) [The Philosophy of Ramda](https://github.com/ramda/ramda)
* [Koa Examples](https://github.com/koajs/examples)
  * [Introduction to Generators & Koa.js: Part 1](http://code.tutsplus.com/tutorials/introduction-to-generators-koajs-part-1--cms-21615)
  * [Introduction to Generators & Koa.js: Part 2](http://code.tutsplus.com/tutorials/introduction-to-generators-koajs-part-2--cms-21756)
* [Co](https://github.com/tj/co) - Generator based control flow goodness for nodejs and the browser, using promises, letting you write non-blocking code in a nice-ish way. 

> :octocat:: Better to understand before moving ahead with await/async approach

### WATCH & STUDY Functional Reactive Alternative
- [ ] There's always smth else ...
* (fun) [lazy.js](http://danieltao.com/lazy.js/)
* (fun) [bacon.js](https://github.com/baconjs/bacon.js)
* [Circle.js](http://cycle.js.org/) [@andrestaltz](https://twitter.com/andrestaltz)
  * [UNIDIRECTIONAL USER INTERFACE ARCHITECTURES](http://staltz.com/unidirectional-user-interface-architectures.html)
   

### TOOLS & LIBRARIES
* [npm](https://docs.npmjs.com/getting-started/what-is-npm) 
* [Webpack] (https://webpack.github.io/)
* [Babel Learn ES2015](https://babeljs.io/docs/learn-es2015/)

> Babel should be able to power minifiers, linters, formatters, syntax highlighters, code completion tools, type checkers, codemod tools, and every other tool to be using the same foundation to do their job better than ever before.

- [ ] Learn how to reduce css
- [ ] Learn how to split js code for faster downloads 
* [Mocha](http://mochajs.org) - simple, flexible, fun javascript test framework for node.js & the browser. (BDD, TDD, QUnit styles via interfaces)
* [CSS Modules](https://github.com/css-modules/css-modules) 
  * BEST [CSS Modules Welcome to the Future](http://glenmaddern.com/articles/css-modules)
  * - [ ] What's next? SASS >> PostCSS >> CSS Modules >> ???
  * [PostCSS vs SASS: Breaking up with Sass: it’s not you, it’s me](http://benfrain.com/breaking-up-with-sass-postcss/)
    * [SASS](https://github.com/sass/sass)
    * [PostCSS](https://github.com/postcss/postcss)
* [JSCS — JavaScript Code Style](http://jscs.info/) from bunch of Russians ;))
* [ESLint: The Next-Generation JavaScript Linter](http://www.smashingmagazine.com/2015/09/eslint-the-next-generation-javascript-linter/)
* [Airbnb JavaScript Style Guide() {](https://github.com/airbnb/javascript)
* [Debugging Memory Leaks in Node.js Applications](http://www.toptal.com/nodejs/debugging-memory-leaks-node-js-applications)

### Articles And Tutorials
* [DevTools for Redux with hot reloading, action replay, and customizable UI](https://github.com/gaearon/redux-devtools)
* [Tutorial: Handcrafting an Isomorphic Redux Application (With Love)](https://medium.com/@bananaoomarang/handcrafting-an-isomorphic-redux-application-with-love-40ada4468af4)
* [Understanding Redux Middleware](https://medium.com/@meagle/understanding-87566abcfb7a)
* [Redux Middleware: Behind the Scenes](http://briantroncone.com/?p=529)
* [Full-Stack Redux Tutorial - A Comprehensive Guide to Test-First Development with Redux, React, and Immutable](http://teropa.info/blog/2015/09/10/full-stack-redux-tutorial.html) Source [Server](https://github.com/teropa/redux-voting-server) + [Client](https://github.com/teropa/redux-voting-client)
* [Redux best practices](https://medium.com/lexical-labs-engineering/redux-best-practices-64d59775802e)
* [Building a boilerplate for a Koa, Redux, React application including Webpack, Mocha and SASS](http://blog.joanboixados.com/building-a-boilerplate-for-a-koa-redux-react-application-including-webpack-mocha-and-sass/) - This article explains in detail how [this koa-redux-react-boilerplate](https://github.com/mezod/boilerplate-koa-redux-react) was built and the technologies it uses.

### Boilerplates
* [Ripster](https://github.com/vslinko/ripster)
* [Koa :octocat:](https://github.com/koajs/koa)
    * [Isomorphic (Koa + Redux)](https://github.com/khtdr/redux-react-koa-isomorphic-counter-example) :metal:
    * [isomorphic-react-redux-koa](https://github.com/davezuko/isomorphic-react-redux-koa) :metal:
    * [Sliced Haskell fragments](https://github.com/rwilhelm/slices) Universal + RethinkDB + ElasticSearch + lots of good stuff :fire:

### Middleware
* SUPER [react-dom-stream] (https://github.com/aickin/react-dom-stream)
* ???? [redux-effects - tools and middlewares](https://github.com/redux-effects)
* [redux-transduce - Transducer utilities for Redux](https://github.com/acdlite/redux-transduce)
  * [Transducers.js: A JavaScript Library for Transformation of Data](http://jlongster.com/Transducers.js--A-JavaScript-Library-for-Transformation-of-Data)
* [redux-promise - FSA-compliant promise middleware for Redux](https://github.com/acdlite/redux-promise)
* [redux-simple-promise - FSA-compliant promise middleware for Redux with simple behaviour with minimal boilerplate declarations](https://github.com/alanrubin/redux-simple-promise)
  Simple "selector" library for Redux inspired by getters in [NuclearJS](https://github.com/optimizely/nuclear-js.git), [subscriptions](https://github.com/Day8/re-frame#just-a-read-only-cursor) in [re-frame](https://github.com/Day8/re-frame) and this [proposal](https://github.com/gaearon/redux/pull/169) from [speedskater](https://github.com/speedskater).
  * Selectors can compute derived data, allowing Redux to store the minimal possible state.
  * Selectors are efficient. A selector is not recomputed unless one of its arguments change.
  * Selectors are composable. They can be used as input to other selectors.
* [redux-requests - Avoid issuing duplicate HTTP requests](https://github.com/idolize/redux-requests)
* [redux-batched-updates - Batch React updates that occur as a result of Redux dispatches, to prevent cascading renders.](https://github.com/acdlite/redux-batched-updates)
* ??? [redux-thunk - Thunk middleware for Redux](https://github.com/gaearon/redux-thunk)
* ??? [redux-catch-promise - Extended replacement of redux-thunk middleware to supporting async-await functions and implement server-side rendering for React components with async state](https://github.com/DenisIzmaylov/redux-catch-promise)
* [redux-localstorage - Store enhancer that syncs (a subset) of your Redux store state to localstorage.](https://github.com/elgerlambert/redux-localstorage)


### Tools
* Andrew Clark @acdlite https://github.com/acdlite
* [redux-devtools - DevTools for Redux with hot reloading, action replay, and customizable UI](https://github.com/gaearon/redux-devtools)
* READ! [replux - Self contained components and enhancements for Redux](https://github.com/gregthebusker/replux)
* [redux-devtools-gentest-plugin - Generate mocha like tests from redux-devtools session](https://github.com/lapanoid/redux-devtools-gentest-plugin)
* [redux-loader - A high order component for Redux. This components loads resources and passes them to the child components via props](https://github.com/sporto/redux-loader)
* [redux-api - Flux REST API for redux infrastructure](https://github.com/lexich/redux-api)
* [redux-form - An ES7 decorator for forms using Redux and React](https://github.com/erikras/redux-form)
* [redux-optimist - Optimistically apply actions that can be later commited or reverted.](https://github.com/ForbesLindesay/redux-optimist)
* [redux-devtools-diff-monitor - Redux DevTools – Diff Monitor](https://github.com/whetstone/redux-devtools-diff-monitor)

## UI Kits
* [React UI Kit reapp.io](http://reapp.io/)
* [React-Bootstrap](https://react-bootstrap.github.io/)
  * [Bootstrap 2](http://getbootstrap.com/2.3.2/base-css.html#icons) [Bootstrap 3](http://getbootstrap.com/) [Bootstrap 4](http://v4-alpha.getbootstrap.com/)

### Chrome Extensions
* [Redux Chrome Extension](https://github.com/Dharmoslap/redux-chrome-extension)
* [React Chrome Extension Boilerplate](https://github.com/jhen0409/react-chrome-extension-boilerplate)

###  Moji
* :metal: - Universal (Isomorphic)
* :fire: - [Hot Reload](http://gaearon.github.io/react-hot-loader)
* [EMOJI CHEAT SHEET](http://www.emoji-cheat-sheet.com/)
* [Mastering Markdown](https://guides.github.com/features/mastering-markdown/)

### Want more? 
Check original awesome-redux [xgrommx/awesome-redux ;))) ](https://github.com/xgrommx/awesome-redux)