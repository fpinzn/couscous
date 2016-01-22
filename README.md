# CousCous

CSS Regression testing for the ones who prepare for laziness.

## scifi

This is a tool for preventing regression errors in a web based user interface.
This can be accomplished creating diffs between rasterized versions of multiple ui elements. Said elements can come in several levels:

- __atoms__: such as buttons, links, texts, images.
- __molecules__: Composed of atoms.
- __organisms__: Composed of molecules (and atoms?)

Check deeply at http://patternlab.io/

The errors are reported in the level they ocurr.

For the first prototype it will simply report all the difference it found from the last time running, and ask whether it is or not a regression.

## how

It uses https://github.com/johntitus/node-horseman to get the snapshot of the elements.

## example

#### `.snapshot(selectorList, url, cb)`

`selectorList` is a list of `area` elements passed each to  `node-horsemen.crop`:

> `area` can be a string identifying an html element on the screen to crop to, or a getBoundingClientRect object.


Returns a stream of snapshots of the selectors.

```js
  let atoms = ['#name', 'button#chef', 'selector']
  cc.snapshot(atoms, 'localhost:3000/codex')
```
