# dogfinder
##First of all we will set up the tooling.
install node in your machine.use the link https://nodejs.org/en/.
- Node comes with npm.
Next do:
npm init 
This will generate package.json file.This is where dependencies will be tracked.
###i)Tools for high code quality
a) Install prettier -
npm install -D prettier 
OR
npm i -D prettier
-it is used for code formatting
if you want to run it from the command line then -go to scripts in the package.json and add : which runs prettier on any file on any directory inside of the source directory that has js or html extension.
Alternatively go to visual studio code and install prettier from extensions and on its settings check format on save and require config to be on.
to configure prettier create a file called .prettierrc in the root directory and
{} 
in the file meaning that you are going to use the default prettier configs.
###b)install eslint -
npm install -D eslint eslint-config-prettier
it is used for code styling
to condigure prettier add a file in the root called .estlint.json
```
{
  "extends": ["eslint:recommended", "prettier", "prettier/react"],
  "plugins": [],
  "parserOptions": {
    "ecmaVersion": 2018,
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
then you can add:
"lint": "eslint \"src/**/*.{js,jsx}\" --quiet",
to the scripts in the package.json
Then you can install eslint from the extensions in Visual studio code(i mean you can add it in your other editors).
Create a folder called .gitignore and add:
node_modules
.cache/
dist/
.env
.DS_Store
coverage/
.vscode/
This will be used in vscode but not to be added to git.
###c)Install Parcel
It is used for bundling just like webpack but has not configurations.Bundles code together for development environment and for production.
npm install -D parcel-bundler
You then add the below script to package.json
"dev": "parcel src/index.html"
You can then install react and react-dom from the npm registry.
npm i react react-dom
###4)Configuring eslint for react
npm install -D babel-eslint eslint-plugin-import eslint-plugin-jsx-a11y eslint-plugin-react
Then in the package.json should look like:
{
  "extends": [
    "eslint:recommended",
    "plugin:import/errors",
    "plugin:react/recommended",
    "plugin:jsx-a11y/recommended",
    "prettier",
    "prettier/react"
  ],
  "rules": {
    "react/prop-types": 0
  },
  "plugins": ["react", "import", "jsx-a11y"],
  "parserOptions": {
    "ecmaVersion": 2018,
    "sourceType": "module",
    "ecmaFeatures": {
      "jsx": true
    }
  },
  "env": {
    "es6": true,
    "browser": true,
    "node": true
  },
  "settings": {
    "react": {
      "version": "detect"
    }
  }
}
JSX
It is used for code readability.it translates HTML tags into React.createElement calls hence allowing HTML to be used in JavaScript.Anywhere you use JSX, you need to import React.This is because JSX is compiled to React.createElement calls.
Hooks
Used for writing react components.
Configuring EsLint for hooks
npm i -D eslint-plugin-react-hooks
In your .eslint.json file add:
{
  "rules": {
    …,
    "react-hooks/rules-of-hooks": "error"
  },
  "plugins": [
    …,
    "react-hooks"
    ],
}
