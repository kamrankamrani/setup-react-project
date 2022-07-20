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
"format": "prettier --write \"src/**/*.{js,jsx}\""
```
