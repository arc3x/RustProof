# Rustproof

[![Build Status](https://travis-ci.org/Rust-Proof/rustproof.svg?branch=master)](https://travis-ci.org/Rust-Proof/rustproof)

Rustproof is a compiler plugin for the Rust programming language. It generates verification conditions for functions with supplied preconditions(`P`) and postconditions(`Q`). That is, given a supplied postcondition on a function, rustproof uses [predicate transformer semantics](https://en.wikipedia.org/wiki/Predicate_transformer_semantics) to generate a weakest precondition(`WP(S, Q)`) from the postcondition and a body of statements(`S`). The verification condition `P->WP(S,Q)` is then checked for validity by a SMT solver ([z3](https://github.com/Z3Prover/z3)). This process results in a proof of function correctness.

## Dependencies

* `rustc 1.12.0-nightly (2016-08-12)`.

* [z3](https://github.com/Z3Prover/z3)

Your installation of z3 needs to be in your PATH for rustproof to work.

## Supported Rust Language Features

* Integer Arithmetic
    * `isize` and `usize` are **unsupported**
* Boolean Statements
* Assertions (Integer/Boolean)
* If Statements

## Usage

### Including Rustproof in Your Project

Add rustproof as a dependency in `Cargo.toml`
```toml
[dependencies]
rustproof = { git = "https://github.com/Rust-Proof/rustproof.git" }
```

### Using Rustproof

Rustproof uses a function attribute `condition` to allow declaring pre/postcondition.

The attribute is supplied as:
`#[condition(pre=" ", post=" ")]`

See [USAGE](USAGE.md) for a detailed explanation of the attribute system.

See [EXAMPLES](EXAMPLES.md) for example functions with condition attributes.


## Contributors
[Matthew Slocum][slocum]  
[Sami Sahli][sahli]  
[Vincent Schuster][schuster]  
[Michael Salter][salter]  
[Bradley Rasmussen][rasmussen]  
[Drew Gohman][gohman]  
[Matthew O'Brien][obrien]  

[slocum]:https://github.com/arc3x
[sahli]:https://github.com/ssahli
[schuster]:https://github.com/VSchuster
[salter]:https://github.com/salterm
[rasmussen]:https://github.com/bajr
[gohman]:https://github.com/found101
[obrien]:https://github.com/obriematt

## Reporting Issues

Please report all issues on the github [issue tracker][issues].

[issues]:https://github.com/Rust-Proof/rustproof/issues


## License

Rustproof is primarily distributed under the terms of both the MIT license and the Apache License (Version 2.0).

See [LICENSE-APACHE][1], [LICENSE-MIT][2], and [COPYRIGHT][3] for details.

[1]:https://github.com/Rust-Proof/rustproof/blob/master/LICENSE-APACHE
[2]:https://github.com/Rust-Proof/rustproof/blob/master/LICENSE-MIT
[3]:https://github.com/Rust-Proof/rustproof/blob/master/COPYRIGHT
