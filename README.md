##Type definitions for [Ramda](https://github.com/ramda/ramda)

[![Build Status](https://travis-ci.org/donnut/typescript-ramda.svg?branch=master)](https://travis-ci.org/donnut/typescript-ramda)
[![Gitter](https://badges.gitter.im/Join Chat.svg)](https://gitter.im/donnut/typescript-ramda?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

Test with `npm test`.

Pull requests are welcome!

##Usage

Install the typings for node using:
```bash
npm install @types/ramda --saveDev
```
If you use the package through a script tag, use:
```bash
npm install @types/ramda --saveDev --global
```

##Note on placeholders
Due to incompatiblity problems with typescript's typing system, Ramda's placeholder
typing is removed. For binary functions the same functionally can be achieved using
`R.flip`. For example:

```typescript
// using a placeholder ...
R.subtract(*placeholder*, 3);
// ... is the same as
R.flip(R.subtract)(3);
```

In Ramda almost all functions are curried. TypeScript does not natively support
currying, so in cases where we've omitted a combination this might break.
Example of a potential gap:
```typescript
R.insert(2, 'x', [1,2,3,4])
R.insert(2)('x', [1,2,3,4])
R.insert(2, 'x')([1,2,3,4])
R.insert(2)('x')([1,2,3,4]) // => type error!
```

##Status
Typing compatible with ramda version 0.22.1.

##Testing
- unix: `npm test`
- windows: `tsc  --lib es2015 --module amd test.ts --noEmit`
