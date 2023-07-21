# Noir MerkleRoot

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT) [![Nargo Test 🌌](https://github.com/tomoima525/noir-merkle-root/actions/workflows/test.yml/badge.svg)](https://github.com/tomoima525/noir-merkle-root/actions/workflows/test.yml)

**Noir Merkle Root** is a function for calculating merkle root from given inputs. Using Poseidon hash function for hashing.

Works with Noir > 0.7.1.

## Usage

In your `Nargo.toml` file, add the following dependency:

```toml
[dependencies]
noir_merkleroot = { tag = "v0.1.1", git = "https://github.com/tomoima525/noir-merkle-root" }
```

```rust
use dep::noir-merkle-root;
use dep::std;

fn main(
    root: Field,
    leaf: Field,
    path_indices: [Field; 8],
    siblings: [Field; 8],
) {

    // generate merkle root
    let new_root = noir_merkleroot::compute_merkle_root(leaf, path_indices, siblings);
    assert(new_root == root);
}
```

## License

```
MIT License

Copyright (c) 2023 Tomoaki Imai

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the Software), to
deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or
sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED AS IS, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS
IN THE SOFTWARE.
```
