## Steps to reproduce

- Run `npm run tsoa`. It fails because the tsoa CLI (a CJS package) tries to require `tsoa-config.js` which is considered ESM.
- Run `npm run tsoa-cjs`. The require should work with the .cjs extension, but it fails because the tsoa CLI tries to parse `tsoa-config.cjs` as JSON.
- Remove `"type": "module"` and run `npm run tsoa`. The CLI can read the config now. Of course it fails validation, but that is expected because the config is empty.
