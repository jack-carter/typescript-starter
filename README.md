# Typescript Starter

This guide follows along with the online tutorial found at [How to Setup a Typescript + Node.js Project](https://khalilstemmler.com/blogs/typescript/node-starter-project/)

## Before you begin you'll need ...

### Node Version Manager (nvm)
### Node Package Manager (npm)
### A Git local install
### A GitHub account 
### A GitHub repository you want to upload to

## Creating the Basic Project Shell

```
mkdir typescript-starter
cd typescript-starter
touch README.md
touch .gitignore
git init
git remote add origin https://github.com/jack-carter/typescript-starter.git
git commit -m "Initial commit"
git push -u origin master
npm init -y
touch tsconfig.json
mkdir src
touch src/index.js
```

## npm Packages to Install 

```
npm install --save-dev typescript
npm install --save-dev @types/node
npm install --save-dev ts-node
npm install --save-dev nodemon
```

