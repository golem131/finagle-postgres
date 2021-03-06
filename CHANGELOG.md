# Change Log
All notable changes to this project will be documented in this file.

This project adheres to [Semantic Versioning](http://semver.org/). Note that Semantic Versioning is not
necessarily followed during pre-1.0 development.

## 0.4.1-SNAPSHOT
* Added dependency of finagle-postgres-shapeless on patchless
* Support `Updates` quoting from patchless `Patch` values

## 0.4.0
* Breaking API changes:
  * There is no more `Value` wrapper
  * Decoding a column value is based on the requested type - this means that there is no more `row.get(Int)` method
    (without type arguments). Instead, there is `getAnyOption` which returns an `Option[Any]` of the default type for
    that column's OID.
* Added a new subproject `finagle-postgres-shapeless`, which supports shapeless for boilerplate elimination
* Added a new query DSL under the `finagle-postgres-shapeless` module
* Started an effort for some decent documentation

## 0.3.2
* Added a default monitor which handles most ServerErrors
* Updated response classifier and retry policy to look at SQLSTATE
* Added value encoder/decoder for `Instant`

### 0.3.1
* Converted to Stack-based client
* Service is properly closed on channel disconnect

### 0.2.2
* Update to Finagle 6.39.0
* Fix issue when an error during extended query flow causes connection hangs

### 0.2.0
* Rewrite of encoding and decoding mechanism
* Uses `Param` to encode params, with an implicit conversion available for many types
* Provides binary protocol support for parameters and results
* Changes `timestamp` and `timestamptz` to return as `java.time.LocalDateTime` and `java.time.ZonedDateTime` respectively
* Provides support for `numeric` as `BigDecimal`
* Provides many other native type conversions

### 0.1.0
* SSL support
* Manual transactions support

### 0.0.2
* Prepared statements support
* Async responses logging
* Exceptions handling
* Create and drop table support

### 0.0.1
* Clear-text authentication support
* MD5 authentication support
* Select, update, insert, and delete queries

