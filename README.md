# Typescript Starter

This guide follows along with the online tutorial found at [How to Setup a Typescript + Node.js Project](https://khalilstemmler.com/blogs/typescript/node-starter-project/)

## Before you begin you'll need ...

* Node Version Manager (nvm)
* Node Package Manager (npm)
* A Git local install
* A GitHub account 
* A GitHub repository you want to upload to

## Creating the Basic Project Shell
```
mkdir typescript-starter
cd typescript-starter
touch README.md
npm init -y
```

## Configuring Git Properly
```
git init
git remote add origin https://github.com/jack-carter/typescript-starter.git
git commit -m "New project"
git push -u origin master
```

## `npm` Packages to Install
First we need to ensure that any installed `npm` modules don't make their way into the Git repository.
```
echo "node_modules/" >> .gitignore
```

Now we can begin installing the `npm` packages we'll need.
```
npm install --save-dev typescript
npm install --save-dev @types/node
npm install --save-dev ts-node
npm install --save-dev nodemon
```
## Configure `tsc`
```
npx tsc --init --rootDir src --outDir build --esModuleInterop --resolveJsonModule --lib es6 --module commonjs --allowJs true --noImplicitAny true
```

## Setup the Correct Directories
```
mkdir src
touch src/index.js
```