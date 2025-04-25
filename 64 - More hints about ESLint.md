## More hints about ESLint

In the previous video we were setting up ESLint and we were using `babel-eslint` parser in order to parse the latest version of EcmaScript specification. 
If you were following along and trying to set up ESLint on your computer, you might have seen a few errors in the terminal when running `npm run lint`.

```
Parsing error: require() of ES Module.............
```

It seems `babel-eslint` package has been deprecated and moved to another repository some time ago, that’s why we need 
to replace `babel-eslint` with `@babel/eslint-parser` (which is basically the same package, but located in a different repository).

1. First, we need to uninstall `babel-eslint` by running the following command in your terminal:

```
npm uninstall babel-eslint
```

2. Then we need to install @babel/eslint-parser:

```
npm install --save-dev @babel/eslint-parser
```
3. Then inside `.eslintrc` file we need to replace `"parser": "babel-eslint"` with `"parser": "@babel/eslint-parser"`

4. We also need to add `"requireConfigFile": false` to the parserOptions section of `.eslintrc` file:

```
"parserOptions": {
  "ecmaVersion": "latest",
  "requireConfigFile": false, // add this line
  "sourceType": "module"
}
```

5. You can also change ecmaVersion to 2022 or “latest” as shown above.



6. Inside `package.json` file, we need to change npm script related to ESLint:

```

// before:
    "lint": "eslint ."
 
// after
    "lint": "eslint src"
```

After making these changes you should not get any errors when running `npm run lint` in your terminal.

Have a nice day,

Viktor
