# nodejs-package-starter

${DESCRIPTION}

<!-- ## Usage
```js

```
 -->


## Quick Start

Create the app:
```sh
mkdir /tmp/foo && cd $_;
npm init -y;
```

Since the package is ESM, install ESM:
```sh
npm i -S esm;
```

Install nodejs-package-starter:
```sh
npm i -S nodejs-package-starter;
```

Create main module: 
```sh
vi /tmp/foo/app.js;
```

```js
/* /tmp/foo/app.js */
import {add, sub, div, mul} from 'nodejs-package-starter';
console.log(`add(1,2)=${add(1,2)}`);
console.log(`sub(1,2)=${sub(1,2)}`);
console.log(`div(1,2)=${div(1,2)}`);
console.log(`mul(1,2)=${mul(1,2)}`);
```

Run the main module: 
```sh
cd /tmp/foo/;
node -r esm app;
```

<!-- ## Demo -->


## Unit test the package

Test nodejs-package-starter:
```sh
cd ./node_modules/nodejs-package-starter/;
npm run test;
```


## Reference
- [First npm package release-Qiita](https://qiita.com/TsutomuNakamura/items/f943e0490d509f128ae2#%E5%B1%A5%E6%AD%B4)
- [https://blog.katsubemakito.net/nodejs/publish_npm_package_for_beginners](Introduction to npm package release)


## License

[MIT](LICENSE.txt)



## Author
- Twitter: [@TakuyaMotoshima](https://twitter.com/taaaaaaakuya)
- Github: [TakuyaMotoshima](https://github.com/takuya-motoshima)
mail to: development.takuyamotoshima@gmail.com