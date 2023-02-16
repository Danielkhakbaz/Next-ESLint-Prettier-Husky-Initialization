# In order to setup a _Next.js_ app with _ESLint_, _Prettier_, _Husky_ and also setting a _Git_ Repository, We have to follow these steps below

## Git

- At first, We should delete every Git file using: `rd .git /s/q`
- Then we must initialize our Git in our Project using: `git init`
- Add every single changed files to your Repository: `git add .`
- Commit your changes on your Repository with: `git commit -m ""`
- Create a new Repository on the Github website
- Set the existing Git Repository with your Project using: `git remote add origin GIT_REP_ADDRESS`
- Push all the changes with: `git push -u origin master`

## ESLint

- Add ESLint to your Project: `yarn add eslint`
- Start initializing ESLint for your Project: `yarn run eslint --init`
- These are some suggested rules for your Project:
  `"rules": { "react/jsx-uses-react": "error", "react/jsx-no-unused-vars": "off", "@typescript-eslint/no-unused-vars": ["error"], "react/react-in-jsx-scope": 0, "spaced-comment": ["error", "always", { "markers": ["/"] }] }`
- Add the "next" in the end of all the extends

## Prettier

- Add Prettier to your Project: `yarn add prettier`
- Then add "prettier" to your .eslintrc file as one of the extends
- Install this package for the solving the conflict between ESLint and Prettier using: `yarn add eslint-config-prettier && yarn add eslint-config-next`
- Create a .prettierrc file and start writing your rules as a json
- Suggested rules are:
  `{ "printWidth": 80, "tabWidth": 2, "semi": true, "singleQuote": false, "bracketSpacing": true, "bracketSameLine": false, "trailingComma": "es5", "endOfLine": "lf" }`

## Next.js

- Disable the jsDoc problem in \_app.tsx file with: `eslint-disable-next-line require-jsdoc`
- Add the "next" in the end of all the extends in the eslintrc.json file

## VSCode

- Set your default formatter on VSCode to Prettier - Code Formatter
- Then turn on the FormatOnSave and FormatOnPaste on your settings
- Create a new Folder named .vscode
- Inside that, Create a settings.json
- Start writing these codes as json in the settings.json file:
  `{ "editor.formatOnPaste": true, "editor.formatOnSave": true, "editor.defaultFormatter": "esbenp.prettier-vscode", "editor.codeActionsOnSave": { "source.fixAll.eslint": true, "source.fixAll.format": true } }`

## Husky

- Install husky on your Project: `npx husky-init && yarn`
- Add these lines of scripts to your package.json file:
  `"check-types": "tsc --pretty --noEmit", "check-format": "prettier --check .", "check-lint": "eslint . --ext ts --ext tsx", "check-all": "yarn check-types && yarn check-format && yarn check-lint", "fix": "next lint --fix && prettier --write ."`
- Add these texts from <https://github.com/Danielkhakbaz/Next-ESLint-Prettier-Husky-Initialization/blob/master/.husky/pre-commit> to pre-commit file inside .husky folder
- Just in case You're using yarn instead of npm, You should pay attention to the pre-commit file
