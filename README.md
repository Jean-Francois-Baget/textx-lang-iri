# textx-lang-irirefs

![logos](https://github.com/Jean-Francois-Baget/textx-lang-irirefs/blob/main/img/logos.jpg?raw=true)

The project *textx-lang-irirefs* is a python implementation of the standards [RFC 3987 Internationalized Resource Identifiers](https://www.ietf.org/rfc/rfc3987.txt) and [RFC 3986  Uniform Resource Identifiers](https://www.ietf.org/rfc/rfc3986.txt), relying upon the meta-language [textX](https://github.com/textX/textX). The python package `textxirirefs` provides an iriref/uriref parser, recomposition of parsed irirefs, resolution of a relative iriref/uriref in the context of a base IRI/URI, and will soon provide iriref/uriref normalization.


## Installation

The goal is to install the project as simply as typing `pip install textx-lang-irirefs`, provided you have already installed python. But since the project is not yet available on [PyPI](https://pypi.org/), there will be some more work to do.
* With [git](https://git-scm.com/downloads) installed, just `git clone https://gitlab.inria.fr/jfbaget/textx-lang-irirefs.git` to obtain the project folder *textx-lang-irirefs*. Otherwise, just download and unzip https://gitlab.inria.fr/jfbaget/textx-lang-irirefs/-/archive/main/textx-lang-irirefs-main.zip. Then `cd textx-lang-irirefs`.
* Though [pip](https://pypi.org/project/pip/) should be available by default with your python installation, type `pip --version` to ensure you can use it. According to your system, `pip <args>` may have to be replaced by `pip3 <args>`, `python -m pip <args>` or `python3 -m pip <args>`. Then install the package with `pip install .`
* Use `python -m unittest` to check everything went correctly. 

## irirefresolve

`irirefresolve --help`
```
usage: irirefresolve [-h] [-c] base relative

This command returns the resolution of a relative IRI against a base IRI, 
according to the algorithm standardized in [RFC 3986] URI Generic Syntax. 
When the --compatibility flag is set, an non strict resolution algorithm 
is applied according to prior specifications of partial URI [RFC1630]

positional arguments:
  base                 the IRI against which is resolved the relative
  relative             the relativeIRI to resolve against a base

options:
  -h, --help           show this help message and exit
  -c, --compatibility  non strict resolution when in compatibility mode

From textx-lang-irirefs (0.0dev1), (c)2023 Jean-François Baget, Inria.

```

For instance, `irirefresolve -c "http://www.w3.org/2001/XMLSchema#" "integer"` returns *http://www.w3.org/2001/integer*, an unexpected behaviour when one is used to the turtle syntax.





