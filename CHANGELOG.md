# hashIt CHANGELOG

## 3.1.2

* Remove extraneous `toString` call (performance)

## 3.1.1

* Improve hash uniqueness for HTML elements

## 3.1.0

* Add support for `Generator` (not just `GeneratorFunction`)
* Streamline `typeof`- vs `toString`-driven handling for improved speed for most types

## 3.0.0

* Improve speed (2-4x faster depending on type)
* Smaller footprint (~25% reduction)
* Improve hash accuracy for functions (hash now includes function body)
* Fix issue where stack remained in memory after hash was built
* Add ES transpilation for module-ready build tools

#### BREAKING CHANGES

* If using CommonJS, you need to specify `require('hash-it').default` instead of just `require('hash-it')`
* Hashes themselves may have changed (especially for circular objects)
* Removed `isRecursive` method on `hashIt` object (which was wrongly named to begin with)
  * To specifically handle _circular_ objects (which is what it really did), pass `true` as the second parameter to `hashIt`

## 2.1.2

* Move up isNull check in replacer (improve performance of more likely use-case)

## 2.1.1

* Create isNull utility instead of checking strict equality in multiple places

## 2.1.0

* Overall speed improvement by an average of 18.74% (35.27% improvement on complex objects)

## 2.0.1

* More speed improvements

## 2.0.0

* Use JSON.stringify with replacer as default, without try/catch
* Move use of try/catch with fallback to prune to new `hashIt.withRecursion` method (only necessary for deeply-recursive objects like `window`)
* Reorder switch statement for commonality of use cases
* Leverage typeof in switch statements when possible for performance

## 1.3.1

* Add optimize-js plugin for performance in script version

## 1.3.0

* Add hashIt.isUndefined, hashIt.isNull, and hashIt.isEmpty methods
* Reorder switch statements in replacer and getValueForStringification to reflect most likely to least likely (improves performance a touch)
* Remove "Number" from number stringification
* Leverage prependTypeToString whereever possible
* Include Arguments object class

## 1.2.1

* Calculation of Math hashCode now uses properties
* Fix README

## 1.2.0

* Add hashIt.isEqual method to test for equality
* Prepend all values not string or number with object class name to help avoid collision with equivalent string values

## 1.1.0

* Add support for a variety of more object types
* Fix replacer not using same stringifier for int arrays

## 1.0.0

* Initial release
