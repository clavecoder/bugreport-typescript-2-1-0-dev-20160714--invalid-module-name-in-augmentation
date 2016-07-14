# bugreport-typescript-2-1-0-dev-20160714--invalid-module-name-in-augmentation
typescript@next bug report repo.

## Description

The [What's new in TypeScript][1] wiki page and the [Announcing TypeScript 2.0 Beta][2] blog posting
both indicate that TypeScript 2.x supports **Shorthand ambient module declarations**, yet when I 
attempt to use `declare module 'jsonschema';` for the [`jsonschema`][4] npm package I get

> `error TS2664: Invalid module name in augmentation, module 'jsonschema' cannot be found.`

There is a GitHub issue (Microsoft/TypeScript#8518) that recommends getting the latest nightly build, but I 
have the latest and still get the problem. How can this be resolved?

## Steps to reproduce
1. Navigate to a parent folder
1. Clone repo
   > `git clone https://github.com/clavecoder/bugreport-typescript-2-1-0-dev-20160714--invalid-module-name-in-augmentation.git`
1. `cd` to repo
1. Install packages
   > `npm install`
1. Build project
   > `npm run build`

## Result
> error TS2664: Invalid module name in augmentation, module 'jsonschema' cannot be found.
>
> error TS2307: Cannot find module 'jsonschema'.

### Output

```
c:\git\clavecoder\bugreport-typescript-2-1-0-dev-20160714--invalid-module-name-in-augmentation>npm run build

> bugreport-typescript-2-1-0-dev-20160714--invalid-module-name-in-augmentation@0.0.0 build c:\git\clavecoder\bugreport-typescript-2-1-0-dev-20160714--invalid-module-name-in-augmentation
> tsc

modules/test-module/src/test.ts(1,16): error TS2664: Invalid module name in augmentation, module 'jsonschema' cannot be found.
modules/test-module/src/test.ts(3,23): error TS2307: Cannot find module 'jsonschema'.

npm ERR! Windows_NT 10.0.10586
npm ERR! argv "C:\\Program Files\\nodejs\\node.exe" "C:\\Program Files\\nodejs\\node_modules\\npm\\bin\\npm-cli.js" "run" "build"
npm ERR! node v6.3.0
npm ERR! npm  v3.10.3
npm ERR! code ELIFECYCLE
npm ERR! bugreport-typescript-2-1-0-dev-20160714--invalid-module-name-in-augmentation@0.0.0 build: `tsc`
npm ERR! Exit status 2
npm ERR!
npm ERR! Failed at the bugreport-typescript-2-1-0-dev-20160714--invalid-module-name-in-augmentation@0.0.0 build script 'tsc'.
npm ERR! Make sure you have the latest version of node.js and npm installed.
npm ERR! If you do, this is most likely a problem with the bugreport-typescript-2-1-0-dev-20160714--invalid-module-name-in-augmentation package,
npm ERR! not with npm itself.
npm ERR! Tell the author that this fails on your system:
npm ERR!     tsc
npm ERR! You can get information on how to open an issue for this project with:
npm ERR!     npm bugs bugreport-typescript-2-1-0-dev-20160714--invalid-module-name-in-augmentation
npm ERR! Or if that isn't available, you can get their info via:
npm ERR!     npm owner ls bugreport-typescript-2-1-0-dev-20160714--invalid-module-name-in-augmentation
npm ERR! There is likely additional logging output above.

npm ERR! Please include the following file with any support request:
npm ERR!     c:\git\clavecoder\bugreport-typescript-2-1-0-dev-20160714--invalid-module-name-in-augmentation\npm-debug.log

c:\git\clavecoder\bugreport-typescript-2-1-0-dev-20160714--invalid-module-name-in-augmentation>
```


[1]: https://github.com/Microsoft/TypeScript/wiki/What's-new-in-TypeScript
[2]: https://blogs.msdn.microsoft.com/typescript/2016/07/11/announcing-typescript-2-0-beta/
[3]: https://github.com/Microsoft/TypeScript/wiki/What's-new-in-TypeScript#declarationsdts
[4]: https://www.npmjs.com/package/jsonschema
