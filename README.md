# nodejs-package-starter

This is a start kit that creates an ES Modules format library that runs on node.js.

## Create your library.

1. Create project.

    ```sh
    mkdir yourLibrary && cd $_;
    ```

1. Create project configuration file.

    Execute the following command.  
    This will create package.json at the root of the project.  

    ```sh
    npm init -y;
    ```

    Open package.json and edit as follows.  

    ```js
    ...
    "main": "src/yourLibrary.js",
    ...
    ```

    |Name|Value|Description|
    |--|--|--|
    |main|src/yourLibrary.js|The main field is a module ID that is the primary entry point to your program.|

1. Install required packages.

    ```sh
    npm i -S esm && npm i -D jest @babel/preset-env;
    ```

    |Name|Description|
    |--|--|
    |esm|Necessary for executing modules in ES Modules format with node.js.|
    |jest|Jest is a library for testing JavaScript code.|
    |@babel/preset-env|Compile the code under test from the latest specification to ECMAScript 5 so that it can be tested with Jest|

1. Create a library module.

    Create a directory to store source files.  

    ```sh
    mkdir src;
    ```

    Submodule that calculates the subtraction.  

    ```js
    // src/add.js
    /**
     * Sum two values
     */
    export default function (a, b) {
      return a + b;
    }
    ```

    Submodule that calculates the addition.  

    ```js
    // src/sub.js
    /**
     * Diff two values
     */
    export default function (a, b) {
      return a - b;
    }
    ```

    Main module that imports multiple modules and exports a single library.  

    ```js
    // src/yourLibrary.js
    import add from './add';
    import sub from './sub';
    export {add, sub};
    ```    

1. Let's run the library on node.

    Run the following command.  

    ```sh
    node -r esm -e "\
        import {add} from './src/yourLibrary';
        console.log('1+2=' + add(1,2));";# 1+2=3
    ```

1. Setting up and running unit tests.  

    Then, Create add.test.ts and sub.test.ts files in the src directory.  
    This will contain our actual test.  

    ```js
    // src/add.test.js
    import {add} from './yourLibrary';
    test('add 1 + 2 to equal 3', () => {
      expect(add(1, 2)).toBe(3);
    });
    ```

    ```js
    // src/sub.test.js
    import {sub} from './yourLibrary';
    test('sub 2 - 1 to equal -1', () => {
      expect(sub(1, 2)).toBe(-1);
    });
    ```

    Add .babelrc to the project root and add the following content.

    ```sh
    { "presets": ["@babel/preset-env"] }
    ```

    Open your package.json and add the following script.  

    ```js
    ...
    "scripts": {
      "test": "jest"
    ...
    ```

    Run the test.  

    ```sh
    npm run test;
    ```

    Jest will print this message.  
    You just successfully wrote your first test.  

    ```sh
    PASS  src/add.test.js
    PASS  src/sub.test.js

    Test Suites: 2 passed, 2 total
    Tests:       2 passed, 2 total
    Snapshots:   0 total
    Time:        1.329s
    Ran all test suites.
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

1. Setting files to be excluded from publishing

    Create an .npmignore file at the root of the project.  

    ```
    .npmignore
    ```

    Add node_modules and package-lock.json to .npmignore not to publish.

    ```
    node_modules/
    package-lock.json
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
    git commit -am 'Update something';
    git push;
    ```

1. Increase version

    ```sh
    npm version patch -m "Update something";
    ```

1. Create a new version tag on Github

    ```sh
    git push --tags;
    ```

1. Publish to npm

    ```sh
    npm publish;
    ```

## Try this library

1. Create project.

    ```sh
    mkdir myapp && cd $_;
    ```

1. Create project configuration file.

    ```sh
    npm init -y;
    ```

1. Install this library and esm.

    ```sh
    npm i -S nodejs-package-starter esm;
    ```

1. Create a test module.

    Add library execution test module to project root.  
 
    ```sh
    touch app.js;
    ```

    Add content:  

    ```js
    /* app.js */
    import {add, sub} from 'nodejs-package-starter';
    console.log(`1+2=${add(1,2)}`);// 1+2=3
    console.log(`1-2=${sub(1,2)}`);// 1-2=-1
    ```

1. Run the test module.  

    ```sh
    node -r esm app;
    ```

## License
[MIT](LICENSE.txt)

## Author
- Twitter: [@TakuyaMotoshima](https://twitter.com/taaaaaaakuya)
- Github: [TakuyaMotoshima](https://github.com/takuya-motoshima)
mail to: development.takuyamotoshima@gmail.com
