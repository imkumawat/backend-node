# backend-node

NodeJs backend server

1.  How to setup basic code setup?

            1.1 Install following VS Code extension

                 Prettier from https://prettier.io/
                 ESLint from https://www.microsoft.com/en-in/
                 Codeium from https://codeium.com/
                 Code Spell Checker from https://streetsidesoftware.com/
                 GitLens from https://gitkraken.com/

            1.2 Add following files in project directory

                 File name => .eslintrc.json
                 File Content =>
                 {
                 "env": {
                 "browser": true,
                 "commonjs": true,
                 "es2021": true,
                 "node": true
                 },
                 "extends": ["plugin:security/recommended", "airbnb-base", "prettier"],
                 "overrides": [],
                 "parserOptions": {
                 "ecmaVersion": "latest"
                 },
                 "rules": {
                 "no-console": 2,
                 "no-unused-vars": 2,
                 "no-await-in-loop": 2,
                 "no-return-await": 2,
                 "import/no-extraneous-dependencies": 0,
                 "camelcase": 2,
                 "no-param-reassign": 0,
                 "security/detect-object-injection": 0
                 }
                 }

                 File name => .eslintignore
                 File Content =>
                 /node_modules
                 .eslintcache

                 File name => .prettierrc
                 File Content =>
                 {
                 "printWidth": 80,
                 "tabWidth": 2,
                 "singleQuote": false,
                 "semi": true,
                 }

            1.3 Install following dev dependencies in your project's Git Repo

                 eslint, eslint-config-airbnb-base, eslint-config-prettier, eslint-plugin-import,
                 eslint-plugin-security, husky, lint-staged, nodemon, prettier, cross-env

            1.4 Add/Update following element in package.json

                    "scripts": {
                    "start": "node src/server.js",
                    "dev": "cross-env NODE_ENV=development env=localhost nodemon src/server.js",
                    "lint": "npx lint-staged",
                    "prepare": "husky install"
                    },

                    "lint-staged": {
                    "\*.js": [
                    "prettier --write",
                    "eslint --cache --fix"
                    ]
                    }

            1.5 Open terminal in project directory and execute follwing commands

                npm run prepare
                npx husky add .husky/pre-commit "npm run lint"
                git add .
                git commit -m "Keep calm and commit"

                Note; If needed to add hook for "git push" then use like this
                      npx husky add .husky/pre-push "npm run lint"
                      Search on internet for more.

Reference links =>
https://github.com/typicode/husky
