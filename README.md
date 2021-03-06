# Typescript Starter

This guide follows along with the online tutorial found at [How to Setup a Typescript + Node.js Project](https://khalilstemmler.com/blogs/typescript/node-starter-project/)

## Before you begin you'll need ...

* A GitHub account 
* A GitHub repository you want to upload to
* A `git` local install
* Node Version Manager (`nvm`)
* Node Package Manager (`npm`)

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
npm install --save-dev rimraf
```
## Configure `tsc`
```
npx tsc --init --rootDir src --outDir build --esModuleInterop --resolveJsonModule --lib es6 --module commonjs --allowJs true --noImplicitAny true
```

## Setup the Correct Directories
Tell Git to ignore any and all files under the `build/` directory
```
echo "build/" >> .gitignore
```

Now create the source directories we specified in the `tsc` configuration above.
```mkdir src
touch src/index.ts
```

## Configure 'nodemon'
Create a `nodemon.json` file (like the one in this project).

## Add `npm` Commands
We'l be adding two commands to our `package.json` file in the `scripts` section.
```
"build": "rimraf ./build && tsc",
"start:dev": "nodemon",
"start": "npm run build && node build/index.js"
```

## Run the System
Now you can the solution in `development` mode.
```
npm run start:dev
```
Or in `production` mode.
```
npm run start
```

## Adding ESLint
First install the `npm` packages we'll need.
```
npm install --save-dev eslint
npm install --save-dev @typescript-eslint/parser
npm install --save-dev @typescript-eslint/eslint-plugin
```
Now create the `.eslintrc` file as we have in this project.

And tell ESLint the files you DON'T want it looking at.
```
echo "node_modules" >> .eslintignore
echo "dist" >> .eslintignore
```
And finally add an `npm` command in the `scripts` block of `package.json`.
```
"lint": "eslint . --ext .ts"
```
So that you can now easily run ESLint by using the following.
```
npm run lint
```

