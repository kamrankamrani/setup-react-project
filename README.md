# React project setup tools ( in order )

## 1. npm init

use `npm i` in the root of the project. ( where src folder is there )

## 2. Prettier

install prettier
```
npm i -D prettier
```
create a `.prettierrc` file. put minimal configiration there:

```
{}
```

add in script section a command in the `package.json` file:

```
"format": "prettier --write \"src/**/*.{js,jsx}\"",
```
the line above means that prettier format code for the src folder. ( of course you have vs code extension ).

later you can use `npm run format` to format your code.

## 3. eslint

install eslint
```
npm install -D eslint eslint-config-prettier
```
you can use `7.18.0` and `8.1.0` respectively.

create a file `.eslintrc` and put the code there:
```
{
  "extends": ["eslint:recommended", "prettier"],
  "plugins": [],
  "parserOptions": {
    "ecmaVersion": 2022,
    "sourceType": "module",
    "ecmaFeatures": {
      "jsx": true
    }
  },
  "env": {
    "es6": true,
    "browser": true,
    "node": true
  }
}
```
finally add the command in script section in `package.json`:
```
"lint": "eslint \"src/**/*.{js,jsx}\" --quiet",
```
later, you can use `npm run lint`.

### eslint-react & react-hooks

install this plugins:
```
npm i -D eslint-plugin-import eslint-plugin-jsx-a11y eslint-plugin-react eslint-plugin-react-hooks
```

then, update _`eslintrc`_. update `extends` array:
```
"extends": 
[
		"eslint:recommended",
		"plugin:import/errors",
		"plugin:react/recommended",
		"plugin:jsx-a11y/recommended",
		"plugin:react-hooks/recommended",
		"prettier"
]
```
add this **top level** `rules` object:
```
"rules": {
    "react/prop-types": 0,
    "react/react-in-jsx-scope": 0
}
```
and update your `plugin` section: 
```
"plugins": ["react" , "jsx-a11y" , "import"]
```
finally add this **top level** setting to the file:
```
"settings": {
    "react": {
        "version": "detect"
    }
}
```

## 4. Git

after `git init` and if you want create a new repo in github and after `git push` , add a `.gitignore` file and put:
```
node_modules
.parcel-cache/
dist/
.env
.DS_Store
coverage/
.vscode/
```
in there.

## 5. Parcel

install parcel

```
npm i -D parcel
```
parcel version 2 is good for me.

in the `package.json` and in the `script` section add the entry point of your application(maybe it's in the public folder):
```
"dev": "parcel src/index.html"
```
and later you can enter `npm run dev`.

## 6. Babel

install babel:
```
npm install -D @babel/core @babel/preset-react
```

create a file `.babelrc` and add this:
```
{
  "presets": [
    [
      "@babel/preset-react",
      {
        "runtime": "automatic"
      }
    ]
  ]
}
```
finally add this in `package.json`:
```
{
  …
  "browserslist": [
    "last 2 Chrome versions"
  ]
}
```
**remember change this line when deploy. help in:** (https://browserslist.dev/).

## 7. Install React and React-DOM

install packages to start:

```
npm install react react-dom
```
