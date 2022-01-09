# In order to setup a _Next.js_ app with _ESLint_, _Prettier_, _Husky_ and also setting a _Git_ Repository, We have to follow these steps below

## Git

- At first, We should delete every Git file using: **rd .git /s/q**
- Then we must initialize our Git in our Project using: **git init**
- Add every single changed files to your Repository: **git add .**
- Commit your changes on your Repository with: **git commit -m ""**
- Create a new Repository on the Github website
- Set the existing Git Repository with your Project using: **git remote add origin GIT_REP_ADDRESS**
- Push all the changes with: **git push -u origin master**

## ESLint

- Add ESLint to your Project: **yarn add eslint**
- Start initializing ESLint for your Project: **yarn run eslint --init**
- These are some suggested rules for your Project:
  `"rules": { "react/jsx-uses-react": "error", "react/jsx-uses-vars": "error", "spaced-comment": ["error", "always", { "markers": ["/"] }] }`

## Prettier

- Add Prettier to your Project: **yarn add prettier**
- Then add "prettier" to your .eslintrc file as one of the extends
- Install this package for the solving the conflict between ESLint and Prettier using: **yarn add eslint-config-prettier**
- Create a .prettierrc file and start writing your rules as a json
- Suggested rules are:
  `{ "printWidth": 80, "tabWidth": 2, "semi": true, "singleQuote": false, "bracketSpacing": true, "bracketSameLine": true, "trailingComma": "es5", "endOfLine": "lf" }`

## Next.js

- Add the "next" in the end of all the extends
- Disable the jsDoc problem in \_app.tsx file with: **eslint-disable-next-line require-jsdoc**

## VSCode

- Set your default formatter on VSCode to Prettier - Code Formatter
- Then turn on the FormatOnSave and FormatOnPaste on your settings
- Create a new Folder named .vscode
- Inside that, Create a settings.json
- Start writing these codes as json in the settings.json file:
  {
  "editor.formatOnPaste": true,
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.codeActionsOnSave": {
  "source.fixAll.eslint": true,
  "source.fixAll.format": true
  }
  }

## Husky

- Install husky on your Project: **npx husky-init && yarn**
- Add these lines of scripts to your package.json file:
  {
  "check-types": "tsc --pretty --noEmit",
  "check-format": "prettier --check .",
  "check-lint": "eslint . --ext ts --ext tsx",
  "format": "prettier --write .",
  "test-all": "yarn format && yarn check-types && yarn check-format && yarn check-lint && yarn build"
  }
- Add these texts from https://github.com/jarrodwatts/code-like-google/blob/main/.husky/pre-commit to pre-commit file inside .husky folder
