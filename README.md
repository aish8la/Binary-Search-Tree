# Binary Search Tree

A JavaScript binary search tree implementation built from scratch. The tree keeps values in sorted order, ignores duplicate values, and can be rebuilt into a balanced tree after inserts make it unbalanced.

## Features

- Build a balanced tree from an array
- Insert and delete values
- Find nodes by value
- Measure node depth and tree height
- Check whether the tree is balanced
- Rebalance an existing tree
- Traverse the tree in level order, pre-order, post-order, or in-order

## Project Structure

```text
src/
├── bst.js       # Tree implementation
├── driver.js    # Randomized demonstration driver
└── main.js      # Basic usage example
```

## Usage

`Tree` is exported from `src/bst.js`:

```js
import { Tree } from "./src/bst.js";

const tree = new Tree([1, 7, 4, 23, 8, 9, 4, 3, 5, 67]);

tree.insert(10);
tree.delete(7);

const node = tree.find(10);
console.log(node?.data);       // 10
console.log(tree.height());    // Height of the tree
console.log(tree.isBalanced());

const values = [];
tree.inOrder(value => values.push(value));
console.log(values);            // Sorted values

tree.rebalance();
```

The constructor sorts the input and removes duplicates. `insert` also leaves an existing value unchanged.

Traversal methods accept a callback that is called once for each value:

- `levelOrder(callback)`
- `preOrder(callback)`
- `postOrder(callback)`
- `inOrder(callback)`

`depth(value)` returns the number of edges from the root to the value. If the value is not in the tree, it logs a warning and returns `undefined`.

## Run the Demo

This project currently uses native ES modules without a `package.json`. With Node.js installed, run:

```bash
node --experimental-default-type=module src/main.js
```

The demo creates a tree, inserts a value, and prints the tree structure and depth. The randomized `Driver` in `src/driver.js` can also be used to demonstrate balancing and traversals.
