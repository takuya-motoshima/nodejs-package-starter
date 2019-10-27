# nodejs-package-starter

>This is the template for starting a Node.js package

<!-- ## Usage -->

## Quick Start

1. Create the app:

    ```sh
    mkdir /tmp/foo && cd $_;
    npm init -y;
    ```

1. Since the package is ESM, install ESM:

    ```sh
    npm i -S esm;
    ```

1. Install nodejs-package-starter:

    ```sh
    npm i -S nodejs-package-starter;
    ```

1. Create main module: 

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

1. Run the main module: 

    ```sh
    cd /tmp/foo/;
    node -r esm app;
    ```

## Unit test the package
Test nodejs-package-starter:

```sh
cd ./node_modules/nodejs-package-starter/;
npx jest --coverage;
#npm run test;
```

## How to publish a npm package

1. Create an NPM user locally.  
When the command is executed, a '~/.npmrc' file is created and the entered information is stored.

    ```sh
    npm set init.author.name 'Your name';
    npm set init.author.email 'your@email.com';
    npm set init.author.url 'https://your-url.com';
    npm set init.license 'MIT';
    npm set init.version '1.0.0';
    ```

1. Create a user on [npm](https://www.npmjs.com/).  
If the user is not registered yet, enter the new user information to be registered in npm.  
If an npm user has already been created, enter the user information and log in.

    ```sh
    npm adduser;
    ```

1. Create a repository on GitHub and clone.

    ```sh
    git clone https://github.com/your-user/your-repository.git;
    ```

1. Create package information.  
Answer the questions in the command line questionnaire.

    ```sh
    npm init;
    ```

1. Dependent package settings.  
Put the packages required for development.

    ```sh
    npm i -D (package name);
    ```

1. The package necessary for production execution is put as follows.

    ```sh
    npm i -S (package name);
    ```

1. Write the program in the first file to be executed specified by 'entry point' of 'npm init'.

    ```js
    console.log('Hello World!');
    ```

1. Create README.md and describe the package description in Markdown format

    ```sh
    echo '# Your package name' >> README.md;
    ```

1. Push to GitHub.

    ```sh
    git commit -am 'Added main module';
    git push;
    ```

1. Create v1.0.0 tag on GitHub.
    
    ```sh
    git tag -a v1.0.0 -m 'My first version v1.0.0';
    git push origin v1.0.0;
    ```

1. Publish to npm
    
    ```sh
    npm publish;
    ```

## How to upgrade NPM packages

1. Push program changes to github
    
    ```sh
    git commit -am 'Updated module';
    git push;
    ```


1. Increase version

    ```sh
    npm version patch -m 'Updated module'
    ```

1. Create a new version tag on Github

    ```sh
    git push --tags;
    ```

1. Publish to npm
    
    ```sh
    npm publish;
    ```

## Reference
- [First npm package release-Qiita](https://qiita.com/TsutomuNakamura/items/f943e0490d509f128ae2#%E5%B1%A5%E6%AD%B4)
- [Introduction to npm package release](https://blog.katsubemakito.net/nodejs/publish_npm_package_for_beginners)

## License
[MIT](LICENSE.txt)

## Author
- Twitter: [@TakuyaMotoshima](https://twitter.com/taaaaaaakuya)
- Github: [TakuyaMotoshima](https://github.com/takuya-motoshima)
mail to: development.takuyamotoshima@gmail.com