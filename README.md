# ConCert

A framework for smart contract verification in Coq

## How to build


Our development works with Coq 8.9.1. and depends on MetaCoq 1.0~alpha and the
std++ library. These dependencies can be installed through `opam`.

First, install Coq:

```bash
opam install coq.8.9.1
```

Then MetaCoq:

```bash
opam repo add coq-released https://coq.inria.fr/opam/released
opam install coq-metacoq
```
And std++:

```bash
opam repo add iris-dev https://gitlab.mpi-sws.org/iris/opam.git
opam install coq-stdpp
```

After completing the procedures above, `cd` into the artifact directory and run
`make`. By default, `make` will build all the development and the documentation.

## Documentation

The `docs` folder contains the autogenerated `coqdoc`
documentation. We use `CoqdocJS` by Tobias Tebbi
(https://github.com/tebbi/coqdocjs) for better usability and syntax
highlighting. One can show/hide proof using the button on the top
panel. Open [docs/toc.html](./docs/toc.html) to start browsing the
documentation.

## Some highlights

* [theories/Ast.v](./theories/Ast.v) contains definition of the
  ``λsmart`` language (Section 2.2).
* [theories/EvalE.v](./theories/EvalE.v) contains an interpreter for
  ``λsmart`` language (Section 2.2, Figure 2).
* [theories/pcuic/PCUICTranslate.v](./theories/pcuic/PCUICTranslate.v)
    contains the translation from ``λsmart`` expression to PCUIC terms
    (Section 2.3, Figure 3).
* [theories/pcuic/PCUICCorrectness.v](./theories/pcuic/PCUICCorrectness.v)
  contatins proofs of Theorem 1, Corollary 2 and Theorem 3.
* [theories/pcuic/PCUICCorrectnessAux.v](./theories/pcuic/PCUICCorrectnessAux.v)
  contatins proofs of Lemmas 1 and 2.
* [theories/Wf.v](./theories/Wf.v) contains well-formedness conditions (Definition 1)
* [theories/examples/crowdfunding](./theories/examples/crowdfunding)
  contains a crowdfunding contract given as a deep embedding using
  notations and proofs of functional correctness properties on the
  corresponding shallow embedding (Section 3).
* [theories/examples/AcornExamples.v](./theories/examples/AcornExamples.v)
  contains Examples of library code and contracts originating from the
  actual Acorn implementation, including verification of ``Acorn``
  list functions (Section 4).
* [theories/examples/ExecFrameworkIntegration.v](./theories/examples/ExecFrameworkIntegration.v)
  contains integration with the execution framework (instances,
  wrappers) and properties of the crowdfunding contract with relation
  to the execution model (Section 5).
* [smart-contract-interactions](./smart-contract-interactions/) is a
  folder containing the execution framework itself.
* also, see [theories/examples/Demo.v](theories/examples/Demo.v) for
  demonstration of how to use our framework to write definitions using
  the deep embedding, convert them to Coq functions, compute with the
  interpreter and prove simple properties using the shallow embedding.
