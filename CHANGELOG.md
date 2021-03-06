# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).


## 4.2.0 - 2020-03-29
### Added
*  Added Django 3.0 compatibility.
### Removed
*  Removed Django 2.0 and 2.1 compatibility. These are EOL.


## 4.1.0 - 2019-08-28
### Added
* `UserBasedFlexQuery` can now be configured to handle anonymous users like no user.


## 4.0.0 - 2019-08-08
### Added
* `FlexQuery.from_func` can now set additional attributes on the newly created type
### Changed
* Renamed `contrib.for_user` to `contrib.user_based`
* Made the behavior of `UserBasedFlexQuery` when no user was given configurable


## 3.0.0 - 2019-08-08
### Added
* Added `django_flexquery.contrib.for_user.ForUserFlexQuery`
### Changed
* Changed directory structure of unittests
* Renamed ``FlexQuery.from_q`` to ``from_func``
* ``FlexQuery`` super-types (those without function attached) don't have a custom
  metaclass anymore. This has no effect on the API.


## 2.0.0 - 2019-08-06
## Added
* Added `FlexQuery.call_bound()` method as a hook to preprocess custom arguments.
### Changed
* Significantly simplified API:
  It's straightforward to build a Q function that produces a sub-query, hence
  `FlexQuery` types can now only be created from Q functions, simplifying both code
  and unittests a lot.
* Custom functions now get the base QuerySet as first argument.


## 1.0.1 - 2019-07-29
### Added
* Initial release
