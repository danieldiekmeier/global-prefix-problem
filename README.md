# @esm/std problem with global-prefix

This uses
@std/esm 0.21.4
global-prefix 1.0.2

To reproduce:

```
git clone git@github.com:danieldiekmeier/global-prefix-problem.git
cd global-prefix-problem
npm i

# this will exit and show "before" and "after":
node index.js

# this will run forever and only show "before":
node -r @esm/std index.js
```

I think the problem lies within `node_modules/global-prefix/index.js`: `tryNpmPath` is called in an infinite loop.
