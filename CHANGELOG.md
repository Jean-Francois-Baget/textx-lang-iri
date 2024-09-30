# Changelog

All notable changes to `textx-lang-irirefs` will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.0.dev7] -- 2024-04-12

### Fixed

- Added the missing `IRIRefResolveError` exception.

### Added

- The method `recompose` in class `IRIReference` now admits an optional parameter `absolute = False`. When this parameter is called with value `True`, the fragment identifier is omitted from the recomposition.

### Changed

- the fields `query` and `fragment` now correctly contain `"query"` or `"fragment"` instead of `"?query"` or `"?fragment"`

## [0.0.dev6] -- 2023-10-29

### Fixed

- IRegNames now correctly accept an empty input 

## [0.0.dev5] -- 2023-10-18

### Changed

- changed the method `resolve(self, base)` in class `IRIReference` to `resolve(self, relative)` in class `IRI`.
- in line with the previous change, the resolve command-line script now accepts `irirefresolve [-h] [-c] base relative` instead of `irirefresolve [-h] [-c] relative base` 

### Added

- in line with the previous change, added a method `resolve_seglist(self, seglist)` in class `ÌRI`, allowing to write:
```python
base = parser.model_from_str('http://www.lirmm.fr')
resolved = base.resolve_seglist(['foo', 'bar'])
print(resolved.recompose)
```
to obtain `http://www.lirmm.fr/foo/bar`



## [0.0.dev4] -- 2023-10-12

### Changed

- The root of the grammar is no more an IRIRef, but a IRIRefContainer, in order to allow for an IRIRef to have a parent object.


## [0.0.dev3] -- 2023-10-11

### Added 
    
- scheme based normalization 

### Changed

- The method `resolve` of class `textxirirefs.iri.IRIRef` now returns a model instead of a string. Tests and irrefresolve modified according to that change.
- Changed grammars and classes to properly classify AbsoluteURI and AbsoluteIRI programmatically, for efficiency reasons.

### Fixed

- Resolving `bar` against `//foo` now correctly returns `//foo/bar` instead of `//foobar`. [Issue 2](https://gitlab.inria.fr/jfbaget/textx-lang-irirefs/-/issues/2) now closed.
- IRI is now correctly defined and its fragment is optional, an important feature when importing the grammar. 

## [0.0.dev2] -- 2023-10-10

### Added 

- Added the `irirefresolve` command.

## [0.0.dev1] -- 2023-10-10

### Added

- Initial commit.

