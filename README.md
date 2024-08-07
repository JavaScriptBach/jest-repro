# jest-repro

This documents a bug with Jest's subpath imports and wildcards.

## Steps
1. cd test
2. npm ci
3. npx jest

## Expected
The correct path (./src/asdf/css.ts) is resolved.

## Actual
The wrong path is resolved:
```
   Cannot find module '/Users/philliphuang/jest-repro/test/src/asdf.css' from '/Users/philliphuang/jest-repro/test/src'

    > 1 | import "#test/asdf/css.ts";
        | ^
      2 |
      3 | it("passes", () => undefined);
      4 |

      at resolveSync (node_modules/resolve/lib/sync.js:111:15)
      at Object.<anonymous> (src/foo.test.ts:1:1)
```