# api documentation for  [redux-persist (v4.6.0)](https://github.com/rt2zz/redux-persist)  [![npm package](https://img.shields.io/npm/v/npmdoc-redux-persist.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-redux-persist) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-redux-persist.svg)](https://travis-ci.org/npmdoc/node-npmdoc-redux-persist)
#### persist and rehydrate redux stores

[![NPM](https://nodei.co/npm/redux-persist.png?downloads=true)](https://www.npmjs.com/package/redux-persist)

[![apidoc](https://npmdoc.github.io/node-npmdoc-redux-persist/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-redux-persist_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-redux-persist/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-redux-persist/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-redux-persist/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "rt2zz",
        "email": "zack@root-two.com"
    },
    "ava": {
        "require": [
            "babel-register",
            "babel-polyfill"
        ],
        "babel": "inherit"
    },
    "bugs": {
        "url": "https://github.com/rt2zz/redux-persist/issues"
    },
    "dependencies": {
        "json-stringify-safe": "^5.0.1",
        "lodash": "^4.17.4",
        "lodash-es": "^4.17.4"
    },
    "description": "persist and rehydrate redux stores",
    "devDependencies": {
        "ava": "^0.18.1",
        "babel-cli": "^6.22.2",
        "babel-core": "^6.22.1",
        "babel-eslint": "^7.1.1",
        "babel-loader": "^6.2.10",
        "babel-polyfill": "^6.22.0",
        "babel-preset-es2015": "^6.22.0",
        "babel-preset-stage-2": "^6.22.0",
        "cross-env": "^3.1.4",
        "immutable": "^3.8.1",
        "lodash-webpack-plugin": "^0.11.0",
        "redux": "^3.6.0",
        "rimraf": "~2.5.4",
        "standard": "^8.6.0",
        "webpack": "^2.2.1"
    },
    "directories": {},
    "dist": {
        "shasum": "3994793d5f2f38bf02591c9e693e16bf8eae2728",
        "tarball": "https://registry.npmjs.org/redux-persist/-/redux-persist-4.6.0.tgz"
    },
    "files": [
        "es",
        "dist",
        "lib",
        "src",
        "constants.js",
        "storages.js",
        "index.js.flow",
        "index.d.ts"
    ],
    "gitHead": "b1e29b95a2b8bcdc4b74b9f9a76ec2b8f47619d2",
    "homepage": "https://github.com/rt2zz/redux-persist",
    "jsnext:main": "es/index.js",
    "keywords": [
        "redux",
        "redux-middleware",
        "localstorage",
        "redux-persist",
        "redux-storage",
        "redux-rehydrate"
    ],
    "license": "MIT",
    "main": "lib/index.js",
    "maintainers": [
        {
            "name": "rt2zz",
            "email": "zstory@ucla.edu"
        }
    ],
    "module": "es/index.js",
    "name": "redux-persist",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/rt2zz/redux-persist.git"
    },
    "scripts": {
        "build": "npm run build:commonjs && npm run build:es && npm run build:umd && npm run build:umd:min && npm run copy-types",
        "build:commonjs": "cross-env BABEL_ENV=commonjs babel src --out-dir lib",
        "build:es": "cross-env BABEL_ENV=es babel src --out-dir es",
        "build:umd": "cross-env BABEL_ENV=commonjs webpack",
        "build:umd:min": "cross-env BABEL_ENV=commonjs NODE_ENV=production webpack",
        "build:watch": "npm run build:commonjs -- -watch",
        "clean": "rimraf lib dist es",
        "copy-types": "cp -r type-definitions/ lib/ && cp -r type-definitions/ es/",
        "prepublish": "npm run clean && npm run build",
        "test": "standard 'src/**/*.js' 'test/**/*.js' storages.js constants.js && BABEL_ENV=commonjs ava --esnext",
        "test:watch": "npm test -- --watch"
    },
    "standard": {
        "parser": "babel-eslint"
    },
    "typings": "lib/index.d.ts",
    "version": "4.6.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module redux-persist](#apidoc.module.redux-persist)
1.  [function <span class="apidocSignatureSpan">redux-persist.</span>autoRehydrate ()](#apidoc.element.redux-persist.autoRehydrate)
1.  [function <span class="apidocSignatureSpan">redux-persist.</span>createPersistor (store, config)](#apidoc.element.redux-persist.createPersistor)
1.  [function <span class="apidocSignatureSpan">redux-persist.</span>createTransform (inbound, outbound)](#apidoc.element.redux-persist.createTransform)
1.  [function <span class="apidocSignatureSpan">redux-persist.</span>getStoredState (config, onComplete)](#apidoc.element.redux-persist.getStoredState)
1.  [function <span class="apidocSignatureSpan">redux-persist.</span>persistStore (store)](#apidoc.element.redux-persist.persistStore)
1.  [function <span class="apidocSignatureSpan">redux-persist.</span>purgeStoredState (config, keys)](#apidoc.element.redux-persist.purgeStoredState)
1.  object <span class="apidocSignatureSpan">redux-persist.</span>storages

#### [module redux-persist.autoRehydrate](#apidoc.module.redux-persist.autoRehydrate)
1.  [function <span class="apidocSignatureSpan">redux-persist.autoRehydrate.</span>default ()](#apidoc.element.redux-persist.autoRehydrate.default)

#### [module redux-persist.createPersistor](#apidoc.module.redux-persist.createPersistor)
1.  [function <span class="apidocSignatureSpan">redux-persist.createPersistor.</span>default (store, config)](#apidoc.element.redux-persist.createPersistor.default)

#### [module redux-persist.createTransform](#apidoc.module.redux-persist.createTransform)
1.  [function <span class="apidocSignatureSpan">redux-persist.createTransform.</span>default (inbound, outbound)](#apidoc.element.redux-persist.createTransform.default)

#### [module redux-persist.getStoredState](#apidoc.module.redux-persist.getStoredState)
1.  [function <span class="apidocSignatureSpan">redux-persist.getStoredState.</span>default (config, onComplete)](#apidoc.element.redux-persist.getStoredState.default)

#### [module redux-persist.persistStore](#apidoc.module.redux-persist.persistStore)
1.  [function <span class="apidocSignatureSpan">redux-persist.persistStore.</span>default (store)](#apidoc.element.redux-persist.persistStore.default)

#### [module redux-persist.purgeStoredState](#apidoc.module.redux-persist.purgeStoredState)
1.  [function <span class="apidocSignatureSpan">redux-persist.purgeStoredState.</span>default (config, keys)](#apidoc.element.redux-persist.purgeStoredState.default)



# <a name="apidoc.module.redux-persist"></a>[module redux-persist](#apidoc.module.redux-persist)

#### <a name="apidoc.element.redux-persist.autoRehydrate"></a>[function <span class="apidocSignatureSpan">redux-persist.</span>autoRehydrate ()](#apidoc.element.redux-persist.autoRehydrate)
- description and source-code
```javascript
function autoRehydrate() {
  var config = arguments.length > 0 && arguments[0] !== undefined ? arguments[0] : {};

  var stateReconciler = config.stateReconciler || defaultStateReconciler;

  return function (next) {
    return function (reducer, initialState, enhancer) {
      var store = next(liftReducer(reducer), initialState, enhancer);
      return _extends({}, store, {
        replaceReducer: function replaceReducer(reducer) {
          return store.replaceReducer(liftReducer(reducer));
        }
      });
    };
  };

  function liftReducer(reducer) {
    var rehydrated = false;
    var preRehydrateActions = [];
    return function (state, action) {
      if (action.type !== _constants.REHYDRATE) {
        if (config.log && !rehydrated) preRehydrateActions.push(action); // store pre-rehydrate actions for debugging
        return reducer(state, action);
      } else {
        if (config.log && !rehydrated) logPreRehydrate(preRehydrateActions);
        rehydrated = true;

        var inboundState = action.payload;
        var reducedState = reducer(state, action);

        return stateReconciler(state, inboundState, reducedState, config.log);
      }
    };
  }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.redux-persist.createPersistor"></a>[function <span class="apidocSignatureSpan">redux-persist.</span>createPersistor (store, config)](#apidoc.element.redux-persist.createPersistor)
- description and source-code
```javascript
function createPersistor(store, config) {
  // defaults
  var serializer = config.serialize === false ? function (data) {
    return data;
  } : defaultSerializer;
  var deserializer = config.serialize === false ? function (data) {
    return data;
  } : defaultDeserializer;
  var blacklist = config.blacklist || [];
  var whitelist = config.whitelist || false;
  var transforms = config.transforms || [];
  var debounce = config.debounce || false;
  var keyPrefix = config.keyPrefix !== undefined ? config.keyPrefix : _constants.KEY_PREFIX;

  // pluggable state shape (e.g. immutablejs)
  var stateInit = config._stateInit || {};
  var stateIterator = config._stateIterator || defaultStateIterator;
  var stateGetter = config._stateGetter || defaultStateGetter;
  var stateSetter = config._stateSetter || defaultStateSetter;

  // storage with keys -> getAllKeys for localForage support
  var storage = config.storage || (0, _asyncLocalStorage2.default)('local');
  if (storage.keys && !storage.getAllKeys) {
    storage.getAllKeys = storage.keys;
  }

  // initialize stateful values
  var lastState = stateInit;
  var paused = false;
  var storesToProcess = [];
  var timeIterator = null;

  store.subscribe(function () {
    if (paused) return;

    var state = store.getState();

    stateIterator(state, function (subState, key) {
      if (!passWhitelistBlacklist(key)) return;
      if (stateGetter(lastState, key) === stateGetter(state, key)) return;
      if (storesToProcess.indexOf(key) !== -1) return;
      storesToProcess.push(key);
    });

    // time iterator (read: debounce)
    if (timeIterator === null) {
      timeIterator = setInterval(function () {
        if (storesToProcess.length === 0) {
          clearInterval(timeIterator);
          timeIterator = null;
          return;
        }

        var key = storesToProcess[0];
        var storageKey = createStorageKey(key);
        var endState = transforms.reduce(function (subState, transformer) {
          return transformer.in(subState, key);
        }, stateGetter(store.getState(), key));
        if (typeof endState !== 'undefined') storage.setItem(storageKey, serializer(endState), warnIfSetError(key));
        storesToProcess.shift();
      }, debounce);
    }

    lastState = state;
  });

  function passWhitelistBlacklist(key) {
    if (whitelist && whitelist.indexOf(key) === -1) return false;
    if (blacklist.indexOf(key) !== -1) return false;
    return true;
  }

  function adhocRehydrate(incoming) {
    var options = arguments.length > 1 && arguments[1] !== undefined ? arguments[1] : {};

    var state = {};
    if (options.serial) {
      stateIterator(incoming, function (subState, key) {
        try {
          var data = deserializer(subState);
          var value = transforms.reduceRight(function (interState, transformer) {
            return transformer.out(interState, key);
          }, data);
          state = stateSetter(state, key, value);
        } catch (err) {
          if (process.env.NODE_ENV !== 'production') console.warn('Error rehydrating data for key "' + key + '"', subState, err);
        }
      });
    } else state = incoming;

    store.dispatch(rehydrateAction(state));
    return state;
  }

  function createStorageKey(key) {
    return '' + keyPrefix + key;
  }

  // return 'persistor'
  return {
    rehydrate: adhocRehydrate,
    pause: function pause() {
      paused = true;
    },
    resume: function resume() {
      paused = false;
    },
    purge: function purge(keys) {
      return (0, _purgeStoredState2.default)({ storage: storage, keyPrefix: keyPrefix }, keys);
    }
  };
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.redux-persist.createTransform"></a>[function <span class="apidocSignatureSpan">redux-persist.</span>createTransform (inbound, outbound)](#apidoc.element.redux-persist.createTransform)
- description and source-code
```javascript
function createTransform(inbound, outbound) {
  var config = arguments.length > 2 && arguments[2] !== undefined ? arguments[2] : {};

  var whitelist = config.whitelist || null;
  var blacklist = config.blacklist || null;

  function whitelistBlacklistCheck(key) {
    if (whitelist && whitelist.indexOf(key) === -1) return true;
    if (blacklist && blacklist.indexOf(key) !== -1) return true;
    return false;
  }

  return {
    in: function _in(state, key) {
      return !whitelistBlacklistCheck(key) && inbound ? inbound(state, key) : state;
    },
    out: function out(state, key) {
      return !whitelistBlacklistCheck(key) && outbound ? outbound(state, key) : state;
    }
  };
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.redux-persist.getStoredState"></a>[function <span class="apidocSignatureSpan">redux-persist.</span>getStoredState (config, onComplete)](#apidoc.element.redux-persist.getStoredState)
- description and source-code
```javascript
function getStoredState(config, onComplete) {
  var storage = config.storage || (0, _asyncLocalStorage2.default)('local');
  var deserializer = config.serialize === false ? function (data) {
    return data;
  } : defaultDeserializer;
  var blacklist = config.blacklist || [];
  var whitelist = config.whitelist || false;
  var transforms = config.transforms || [];
  var keyPrefix = config.keyPrefix !== undefined ? config.keyPrefix : _constants.KEY_PREFIX;

  // fallback getAllKeys to 'keys' if present (LocalForage compatability)
  if (storage.keys && !storage.getAllKeys) storage = _extends({}, storage, { getAllKeys: storage.keys });

  var restoredState = {};
  var completionCount = 0;

  storage.getAllKeys(function (err, allKeys) {
    if (err) {
      if (process.env.NODE_ENV !== 'production') console.warn('redux-persist/getStoredState: Error in storage.getAllKeys');
      complete(err);
    }

    var persistKeys = allKeys.filter(function (key) {
      return key.indexOf(keyPrefix) === 0;
    }).map(function (key) {
      return key.slice(keyPrefix.length);
    });
    var keysToRestore = persistKeys.filter(passWhitelistBlacklist);

    var restoreCount = keysToRestore.length;
    if (restoreCount === 0) complete(null, restoredState);
    keysToRestore.forEach(function (key) {
      storage.getItem(createStorageKey(key), function (err, serialized) {
        if (err && process.env.NODE_ENV !== 'production') console.warn('redux-persist/getStoredState: Error restoring data for key
:', key, err);else restoredState[key] = rehydrate(key, serialized);
        completionCount += 1;
        if (completionCount === restoreCount) complete(null, restoredState);
      });
    });
  });

  function rehydrate(key, serialized) {
    var state = null;

    try {
      var data = deserializer(serialized);
      state = transforms.reduceRight(function (subState, transformer) {
        return transformer.out(subState, key);
      }, data);
    } catch (err) {
      if (process.env.NODE_ENV !== 'production') console.warn('redux-persist/getStoredState: Error restoring data for key:', key
, err);
    }

    return state;
  }

  function complete(err, restoredState) {
    onComplete(err, restoredState);
  }

  function passWhitelistBlacklist(key) {
    if (whitelist && whitelist.indexOf(key) === -1) return false;
    if (blacklist.indexOf(key) !== -1) return false;
    return true;
  }

  function createStorageKey(key) {
    return '' + keyPrefix + key;
  }

  if (typeof onComplete !== 'function' && !!Promise) {
    return new Promise(function (resolve, reject) {
      onComplete = function onComplete(err, restoredState) {
        if (err) reject(err);else resolve(restoredState);
      };
    });
  }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.redux-persist.persistStore"></a>[function <span class="apidocSignatureSpan">redux-persist.</span>persistStore (store)](#apidoc.element.redux-persist.persistStore)
- description and source-code
```javascript
function persistStore(store) {
  var config = arguments.length > 1 && arguments[1] !== undefined ? arguments[1] : {};
  var onComplete = arguments[2];

  // defaults
  // @TODO remove shouldRestore
  var shouldRestore = !config.skipRestore;
  if (process.env.NODE_ENV !== 'production' && config.skipRestore) console.warn('redux-persist: config.skipRestore has been deprecated
. If you want to skip restoration use 'createPersistor' instead');

  var purgeKeys = null;

  // create and pause persistor
  var persistor = (0, _createPersistor2.default)(store, config);
  persistor.pause();

  // restore
  if (shouldRestore) {
    genericSetImmediate(function () {
      (0, _getStoredState2.default)(config, function (err, restoredState) {
        // do not persist state for purgeKeys
        if (purgeKeys) {
          if (purgeKeys === '*') restoredState = {};else purgeKeys.forEach(function (key) {
            return delete restoredState[key];
          });
        }

        store.dispatch(rehydrateAction(restoredState, err));
        complete(err, restoredState);
      });
    });
  } else genericSetImmediate(complete);

  function complete(err, restoredState) {
    persistor.resume();
    onComplete && onComplete(err, restoredState);
  }

  return _extends({}, persistor, {
    purge: function purge(keys) {
      purgeKeys = keys || '*';
      return persistor.purge(keys);
    }
  });
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.redux-persist.purgeStoredState"></a>[function <span class="apidocSignatureSpan">redux-persist.</span>purgeStoredState (config, keys)](#apidoc.element.redux-persist.purgeStoredState)
- description and source-code
```javascript
function purgeStoredState(config, keys) {
  var storage = config.storage;
  var keyPrefix = config.keyPrefix !== undefined ? config.keyPrefix : _constants.KEY_PREFIX;

  // basic validation
  if (Array.isArray(config)) throw new Error('redux-persist: purgeStoredState requires config as a first argument (found array).
An array of keys is the optional second argument.');
  if (!storage) throw new Error('redux-persist: config.storage required in purgeStoredState');

  if (typeof keys === 'undefined') {
    // if keys is not defined, purge all keys
    return new Promise(function (resolve, reject) {
      storage.getAllKeys(function (err, allKeys) {
        if (err && process.env.NODE_ENV !== 'production') {
          console.warn('redux-persist: error during purgeStoredState in storage.getAllKeys');
          reject(err);
        } else {
          resolve(purgeStoredState(config, allKeys.filter(function (key) {
            return key.indexOf(keyPrefix) === 0;
          }).map(function (key) {
            return key.slice(keyPrefix.length);
          })));
        }
      });
    });
  } else {
    // otherwise purge specified keys
    return Promise.all(keys.map(function (key) {
      return storage.removeItem('' + keyPrefix + key, warnIfRemoveError(key));
    }));
  }
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.redux-persist.autoRehydrate"></a>[module redux-persist.autoRehydrate](#apidoc.module.redux-persist.autoRehydrate)

#### <a name="apidoc.element.redux-persist.autoRehydrate.default"></a>[function <span class="apidocSignatureSpan">redux-persist.autoRehydrate.</span>default ()](#apidoc.element.redux-persist.autoRehydrate.default)
- description and source-code
```javascript
function autoRehydrate() {
  var config = arguments.length > 0 && arguments[0] !== undefined ? arguments[0] : {};

  var stateReconciler = config.stateReconciler || defaultStateReconciler;

  return function (next) {
    return function (reducer, initialState, enhancer) {
      var store = next(liftReducer(reducer), initialState, enhancer);
      return _extends({}, store, {
        replaceReducer: function replaceReducer(reducer) {
          return store.replaceReducer(liftReducer(reducer));
        }
      });
    };
  };

  function liftReducer(reducer) {
    var rehydrated = false;
    var preRehydrateActions = [];
    return function (state, action) {
      if (action.type !== _constants.REHYDRATE) {
        if (config.log && !rehydrated) preRehydrateActions.push(action); // store pre-rehydrate actions for debugging
        return reducer(state, action);
      } else {
        if (config.log && !rehydrated) logPreRehydrate(preRehydrateActions);
        rehydrated = true;

        var inboundState = action.payload;
        var reducedState = reducer(state, action);

        return stateReconciler(state, inboundState, reducedState, config.log);
      }
    };
  }
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.redux-persist.createPersistor"></a>[module redux-persist.createPersistor](#apidoc.module.redux-persist.createPersistor)

#### <a name="apidoc.element.redux-persist.createPersistor.default"></a>[function <span class="apidocSignatureSpan">redux-persist.createPersistor.</span>default (store, config)](#apidoc.element.redux-persist.createPersistor.default)
- description and source-code
```javascript
function createPersistor(store, config) {
  // defaults
  var serializer = config.serialize === false ? function (data) {
    return data;
  } : defaultSerializer;
  var deserializer = config.serialize === false ? function (data) {
    return data;
  } : defaultDeserializer;
  var blacklist = config.blacklist || [];
  var whitelist = config.whitelist || false;
  var transforms = config.transforms || [];
  var debounce = config.debounce || false;
  var keyPrefix = config.keyPrefix !== undefined ? config.keyPrefix : _constants.KEY_PREFIX;

  // pluggable state shape (e.g. immutablejs)
  var stateInit = config._stateInit || {};
  var stateIterator = config._stateIterator || defaultStateIterator;
  var stateGetter = config._stateGetter || defaultStateGetter;
  var stateSetter = config._stateSetter || defaultStateSetter;

  // storage with keys -> getAllKeys for localForage support
  var storage = config.storage || (0, _asyncLocalStorage2.default)('local');
  if (storage.keys && !storage.getAllKeys) {
    storage.getAllKeys = storage.keys;
  }

  // initialize stateful values
  var lastState = stateInit;
  var paused = false;
  var storesToProcess = [];
  var timeIterator = null;

  store.subscribe(function () {
    if (paused) return;

    var state = store.getState();

    stateIterator(state, function (subState, key) {
      if (!passWhitelistBlacklist(key)) return;
      if (stateGetter(lastState, key) === stateGetter(state, key)) return;
      if (storesToProcess.indexOf(key) !== -1) return;
      storesToProcess.push(key);
    });

    // time iterator (read: debounce)
    if (timeIterator === null) {
      timeIterator = setInterval(function () {
        if (storesToProcess.length === 0) {
          clearInterval(timeIterator);
          timeIterator = null;
          return;
        }

        var key = storesToProcess[0];
        var storageKey = createStorageKey(key);
        var endState = transforms.reduce(function (subState, transformer) {
          return transformer.in(subState, key);
        }, stateGetter(store.getState(), key));
        if (typeof endState !== 'undefined') storage.setItem(storageKey, serializer(endState), warnIfSetError(key));
        storesToProcess.shift();
      }, debounce);
    }

    lastState = state;
  });

  function passWhitelistBlacklist(key) {
    if (whitelist && whitelist.indexOf(key) === -1) return false;
    if (blacklist.indexOf(key) !== -1) return false;
    return true;
  }

  function adhocRehydrate(incoming) {
    var options = arguments.length > 1 && arguments[1] !== undefined ? arguments[1] : {};

    var state = {};
    if (options.serial) {
      stateIterator(incoming, function (subState, key) {
        try {
          var data = deserializer(subState);
          var value = transforms.reduceRight(function (interState, transformer) {
            return transformer.out(interState, key);
          }, data);
          state = stateSetter(state, key, value);
        } catch (err) {
          if (process.env.NODE_ENV !== 'production') console.warn('Error rehydrating data for key "' + key + '"', subState, err);
        }
      });
    } else state = incoming;

    store.dispatch(rehydrateAction(state));
    return state;
  }

  function createStorageKey(key) {
    return '' + keyPrefix + key;
  }

  // return 'persistor'
  return {
    rehydrate: adhocRehydrate,
    pause: function pause() {
      paused = true;
    },
    resume: function resume() {
      paused = false;
    },
    purge: function purge(keys) {
      return (0, _purgeStoredState2.default)({ storage: storage, keyPrefix: keyPrefix }, keys);
    }
  };
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.redux-persist.createTransform"></a>[module redux-persist.createTransform](#apidoc.module.redux-persist.createTransform)

#### <a name="apidoc.element.redux-persist.createTransform.default"></a>[function <span class="apidocSignatureSpan">redux-persist.createTransform.</span>default (inbound, outbound)](#apidoc.element.redux-persist.createTransform.default)
- description and source-code
```javascript
function createTransform(inbound, outbound) {
  var config = arguments.length > 2 && arguments[2] !== undefined ? arguments[2] : {};

  var whitelist = config.whitelist || null;
  var blacklist = config.blacklist || null;

  function whitelistBlacklistCheck(key) {
    if (whitelist && whitelist.indexOf(key) === -1) return true;
    if (blacklist && blacklist.indexOf(key) !== -1) return true;
    return false;
  }

  return {
    in: function _in(state, key) {
      return !whitelistBlacklistCheck(key) && inbound ? inbound(state, key) : state;
    },
    out: function out(state, key) {
      return !whitelistBlacklistCheck(key) && outbound ? outbound(state, key) : state;
    }
  };
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.redux-persist.getStoredState"></a>[module redux-persist.getStoredState](#apidoc.module.redux-persist.getStoredState)

#### <a name="apidoc.element.redux-persist.getStoredState.default"></a>[function <span class="apidocSignatureSpan">redux-persist.getStoredState.</span>default (config, onComplete)](#apidoc.element.redux-persist.getStoredState.default)
- description and source-code
```javascript
function getStoredState(config, onComplete) {
  var storage = config.storage || (0, _asyncLocalStorage2.default)('local');
  var deserializer = config.serialize === false ? function (data) {
    return data;
  } : defaultDeserializer;
  var blacklist = config.blacklist || [];
  var whitelist = config.whitelist || false;
  var transforms = config.transforms || [];
  var keyPrefix = config.keyPrefix !== undefined ? config.keyPrefix : _constants.KEY_PREFIX;

  // fallback getAllKeys to 'keys' if present (LocalForage compatability)
  if (storage.keys && !storage.getAllKeys) storage = _extends({}, storage, { getAllKeys: storage.keys });

  var restoredState = {};
  var completionCount = 0;

  storage.getAllKeys(function (err, allKeys) {
    if (err) {
      if (process.env.NODE_ENV !== 'production') console.warn('redux-persist/getStoredState: Error in storage.getAllKeys');
      complete(err);
    }

    var persistKeys = allKeys.filter(function (key) {
      return key.indexOf(keyPrefix) === 0;
    }).map(function (key) {
      return key.slice(keyPrefix.length);
    });
    var keysToRestore = persistKeys.filter(passWhitelistBlacklist);

    var restoreCount = keysToRestore.length;
    if (restoreCount === 0) complete(null, restoredState);
    keysToRestore.forEach(function (key) {
      storage.getItem(createStorageKey(key), function (err, serialized) {
        if (err && process.env.NODE_ENV !== 'production') console.warn('redux-persist/getStoredState: Error restoring data for key
:', key, err);else restoredState[key] = rehydrate(key, serialized);
        completionCount += 1;
        if (completionCount === restoreCount) complete(null, restoredState);
      });
    });
  });

  function rehydrate(key, serialized) {
    var state = null;

    try {
      var data = deserializer(serialized);
      state = transforms.reduceRight(function (subState, transformer) {
        return transformer.out(subState, key);
      }, data);
    } catch (err) {
      if (process.env.NODE_ENV !== 'production') console.warn('redux-persist/getStoredState: Error restoring data for key:', key
, err);
    }

    return state;
  }

  function complete(err, restoredState) {
    onComplete(err, restoredState);
  }

  function passWhitelistBlacklist(key) {
    if (whitelist && whitelist.indexOf(key) === -1) return false;
    if (blacklist.indexOf(key) !== -1) return false;
    return true;
  }

  function createStorageKey(key) {
    return '' + keyPrefix + key;
  }

  if (typeof onComplete !== 'function' && !!Promise) {
    return new Promise(function (resolve, reject) {
      onComplete = function onComplete(err, restoredState) {
        if (err) reject(err);else resolve(restoredState);
      };
    });
  }
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.redux-persist.persistStore"></a>[module redux-persist.persistStore](#apidoc.module.redux-persist.persistStore)

#### <a name="apidoc.element.redux-persist.persistStore.default"></a>[function <span class="apidocSignatureSpan">redux-persist.persistStore.</span>default (store)](#apidoc.element.redux-persist.persistStore.default)
- description and source-code
```javascript
function persistStore(store) {
  var config = arguments.length > 1 && arguments[1] !== undefined ? arguments[1] : {};
  var onComplete = arguments[2];

  // defaults
  // @TODO remove shouldRestore
  var shouldRestore = !config.skipRestore;
  if (process.env.NODE_ENV !== 'production' && config.skipRestore) console.warn('redux-persist: config.skipRestore has been deprecated
. If you want to skip restoration use 'createPersistor' instead');

  var purgeKeys = null;

  // create and pause persistor
  var persistor = (0, _createPersistor2.default)(store, config);
  persistor.pause();

  // restore
  if (shouldRestore) {
    genericSetImmediate(function () {
      (0, _getStoredState2.default)(config, function (err, restoredState) {
        // do not persist state for purgeKeys
        if (purgeKeys) {
          if (purgeKeys === '*') restoredState = {};else purgeKeys.forEach(function (key) {
            return delete restoredState[key];
          });
        }

        store.dispatch(rehydrateAction(restoredState, err));
        complete(err, restoredState);
      });
    });
  } else genericSetImmediate(complete);

  function complete(err, restoredState) {
    persistor.resume();
    onComplete && onComplete(err, restoredState);
  }

  return _extends({}, persistor, {
    purge: function purge(keys) {
      purgeKeys = keys || '*';
      return persistor.purge(keys);
    }
  });
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.redux-persist.purgeStoredState"></a>[module redux-persist.purgeStoredState](#apidoc.module.redux-persist.purgeStoredState)

#### <a name="apidoc.element.redux-persist.purgeStoredState.default"></a>[function <span class="apidocSignatureSpan">redux-persist.purgeStoredState.</span>default (config, keys)](#apidoc.element.redux-persist.purgeStoredState.default)
- description and source-code
```javascript
function purgeStoredState(config, keys) {
  var storage = config.storage;
  var keyPrefix = config.keyPrefix !== undefined ? config.keyPrefix : _constants.KEY_PREFIX;

  // basic validation
  if (Array.isArray(config)) throw new Error('redux-persist: purgeStoredState requires config as a first argument (found array).
An array of keys is the optional second argument.');
  if (!storage) throw new Error('redux-persist: config.storage required in purgeStoredState');

  if (typeof keys === 'undefined') {
    // if keys is not defined, purge all keys
    return new Promise(function (resolve, reject) {
      storage.getAllKeys(function (err, allKeys) {
        if (err && process.env.NODE_ENV !== 'production') {
          console.warn('redux-persist: error during purgeStoredState in storage.getAllKeys');
          reject(err);
        } else {
          resolve(purgeStoredState(config, allKeys.filter(function (key) {
            return key.indexOf(keyPrefix) === 0;
          }).map(function (key) {
            return key.slice(keyPrefix.length);
          })));
        }
      });
    });
  } else {
    // otherwise purge specified keys
    return Promise.all(keys.map(function (key) {
      return storage.removeItem('' + keyPrefix + key, warnIfRemoveError(key));
    }));
  }
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
