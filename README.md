[Learn JS/ES6/ES2015 :game_die:Game First!] (JS.md) or [DevooooOPS with SysOPS](DEVOPS.md)
# Hand-picked Redux Ecosystem

Redux - Predictable state container for JavaScript apps which makes you forget about all other frameworks, tools, ecosystems or even coming [WebAssembly] ( https://medium.com/javascript-scene/what-is-webassembly-the-dawn-of-a-new-era-61256ec5a8f6#.1x0ooowqn). Makes you believe that you are in control on apps state and data flow.

* Redux Mafia: [Dan Abramov](https://github.com/gaearon), [React Europe](https://www.react-europe.org/), [Rackt](https://github.com/orgs/rackt/people)
* [Redux Github](https://github.com/rackt/redux)
* [Documentation of Redux](http://rackt.github.io/redux)

### PACKAGE.JSON
* [React.js](http://facebook.github.io/react)
* [react-redux - React bindings for Redux](https://github.com/rackt/react-redux)
* [redux-router - Redux bindings for React Router – keep your router state inside your Redux store](https://github.com/rackt/redux-router)
* [Immutable.js](https://facebook.github.io/immutable-js/) READ MORE [Notes/Immutable.md](Notes/Immutable.md)
* [superagent](https://github.com/visionmedia/superagent) for isomorphic calls to APIs
* [lodash] (https://lodash.com/docs#map) [:octocat:] (https://github.com/lodash/lodash/blob/master/lodash.js#L31)

### TOOLS & LIBRARIES
* [npm](https://docs.npmjs.com/getting-started/what-is-npm) 
* [Webpack] (https://webpack.github.io/)
- [ ] Learn how to reduce css
- [ ] Learn how to split js code for faster downloads 
- [ ] Research Webpack with JSCS+ESLint+Airbnb
* [Mocha](http://mochajs.org) - simple, flexible, fun javascript test framework for node.js & the browser. (BDD, TDD, QUnit styles via interfaces)
* [Babel Learn ES2015](https://babeljs.io/docs/learn-es2015/)
* [SASS](https://github.com/sass/sass)
* [PostCSS](https://github.com/postcss/postcss)
* [PostCSS vs SASS: Breaking up with Sass: it’s not you, it’s me](http://benfrain.com/breaking-up-with-sass-postcss/)
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
* [redux-devtools - DevTools for Redux with hot reloading, action replay, and customizable UI](https://github.com/gaearon/redux-devtools)
### [ ] Sort
* [redux-tiny-router - A Router made for Redux, stop using the router as a controller it's just state!](https://github.com/Agamennon/redux-tiny-router)
* [redux-devtools-gentest-plugin - Generate mocha like tests from redux-devtools session](https://github.com/lapanoid/redux-devtools-gentest-plugin)
* [redux-action-utils - Factory functions for reducing action creator boilerplate (pun not intended)](https://github.com/insin/redux-action-utils)
* [generator-redux - CLI tools for Redux: next-gen functional Flux/React with devtools](https://github.com/banderson/generator-redux)
* [generator-redux-app - Scaffold out a redux app with counter example and react-router](https://github.com/chentsulin/generator-redux-app)
* [redux-loader - A high order component for Redux. This components loads resources and passes them to the child components via props](https://github.com/sporto/redux-loader)
* [redux-rest - Automatically create Flux action constants, action creators and Redux reducers for your REST API](https://github.com/Kvoti/redux-rest)
* [redux-api - Flux REST API for redux infrastructure](https://github.com/lexich/redux-api)
* [vstack-router - Universal router](https://github.com/vslinko/vstack-router)
* [redux-ecommerce - E-commerce flux with redux](https://github.com/Tom-Alexander/redux-ecommerce)
* [redux-form - An ES7 decorator for forms using Redux and React](https://github.com/erikras/redux-form)
* [https://github.com/calesce/redux-slider-monitor](https://github.com/calesce/redux-slider-monitor)
* [updeep - Easily update nested frozen objects and arrays in a declarative and immutable manner](https://github.com/substantial/updeep)
* [redux-immutable - Streamlines use of Immutable.js with Redux reducers.](https://github.com/gajus/redux-immutable)
* [redux-import-export-monitor - A monitor for copying your serialized action log to the clipboard, as well as pasting it in from somewhere else](https://github.com/lapanoid/redux-import-export-monitor)
* [icedam - Just-in-time immutability: freezes data sent to views.](https://github.com/winkler1/icedam)
* [react-inline-grid - Predictable flexbox based grid for React using Redux and Immutable-js.](https://github.com/broucz/react-inline-grid)
* [redux-easy-actions - Sugar library for creating Redux or Flux actions](https://github.com/grigory-leonenko/redux-easy-actions)
* [redux-multi - Dispatch multiple actions from one action creator](https://github.com/ashaffer/redux-multi)
* [immu - A tiny, fail-fast, lazy, immutable Javascript objects library](https://github.com/scottcorgan/immu)
* [Generate standard action creators and reducers for CRUD applications](https://github.com/Versent/redux-crud)
* [Redux & ImmutableJs - Integration of Redux & ImmutableJs that 100% conforms Redux standards](https://github.com/indexiatech/redux-immutablejs)
* [redux-tcomb - Immutable and type-checked state and actions for Redux](https://github.com/gcanti/redux-tcomb)
* [redux-react-router-transitions - Attach react-router transitions to arbitrary actions](https://github.com/johanneslumpe/redux-react-router-transitions)
* [redux-optimist - Optimistically apply actions that can be later commited or reverted.](https://github.com/ForbesLindesay/redux-optimist)
* [redux-devtools-diff-monitor - Redux DevTools – Diff Monitor](https://github.com/whetstone/redux-devtools-diff-monitor)
* [redux-store-visualizer - Visualize Redux store in real time](https://github.com/romseguy/redux-store-visualizer)
* [generator-redux - CLI tools for Redux: next-gen functional Flux/React with devtools](https://github.com/banderson/generator-redux)
* [redux-viewmodel - ViewModel wrapping for Redux & React](https://github.com/tdzl2003/redux-viewmodel)
* [redux-utils - Utility functions for Redux](https://github.com/newtack/redux-utils)
* [multireducer - A utility to wrap many copies of a single Redux reducer into a single key-based reducer](https://github.com/erikras/multireducer)
* [subdivide - User defined UI layout: Every pane can be subdivided and any widget assigned to any pane](https://github.com/philholden/subdivide)
* [redux-viewmodel - ViewModel wrapping for Redux & React](https://github.com/tdzl2003/redux-viewmodel)
* [replux - Self contained components and enhancements for Redux](https://github.com/gregthebusker/replux)
* [redux-immutable-utils - Utilities for using Immutable with Redux](https://github.com/aparticka/redux-immutable-utils)
* [redux-governor - A basic tool for quickly creating state managers (actions + reducers) to use with Redux](https://github.com/tshelburne/redux-governor)
* [recompose - A microcomponentization toolkit for React](https://github.com/acdlite/recompose)

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

### More 
Check [TRASH](TRASH.md) or original awesome-redux [xgrommx/awesome-redux ;))) ](https://github.com/xgrommx/awesome-redux)