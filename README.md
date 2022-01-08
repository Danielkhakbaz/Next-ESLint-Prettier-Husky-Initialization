In order to setup a _Next.js_ app with _ESLint_, _Prettier_, _Husky_ and also setting a _Git_ Repository, We have to follow these steps below:

<h3>Git</h3>

- At first, We should delete every Git file using: <strong>rd .git /s/q</strong>
- Then we must initialize our Git in our Project using: <strong>git init</strong>
- Add every single changed files to your Repository: <strong>git add .</strong>
- Commit your changes on your Repository with: <strong>git commit -m ""</strong>
- Create a new Repository on the Github website
- Set the existing Git Repository with your Project using: <strong>git remote add origin GIT_REP_ADDRESS</strong>
- Push all the changes with: <strong>git push -u origin master</strong>

<h3>ESLint</h3>

- Add ESLint to your Project: <strong>yarn add eslint</strong>
- Start initializing ESLint for your Project: <strong>yarn run eslint --init</strong>

<h3>Prettier</h3>

- Add Prettier to your Project: <strong>yarn add prettier</strong>
- Then add "prettier" to your .eslintrc file as one of the extends
- Install this package for the solving the conflict between ESLint and Prettier using: <strong>yarn add eslint-config-prettier</strong>
- Create a .prettierrc file and start writing your rules as a json
- Suggested rules are:
  {
  "printWidth": 80,
  "tabWidth": 2,
  "semi": true,
  "singleQuote": false,
  "bracketSpacing": true,
  "bracketSameLine": true,
  "trailingComma": "es5",
  "endOfLine": "lf"
  }

<h3>VSCode</h3>

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

<h3>Husky</h3>

- Install husky on your Project: <strong>npx husky-init && yarn</strong>
- Add these lines of scripts to your package.json file:
  {
  "check-types": "tsc --pretty --noEmit",
  "check-format": "prettier --check .",
  "check-lint": "eslint . --ext ts --ext tsx",
  "format": "prettier --write .",
  "test-all": "yarn format && yarn check-types && yarn check-format && yarn check-lint && yarn build"
  }
- Add these texts from https://github.com/jarrodwatts/code-like-google/blob/main/.husky/pre-commit to pre-commit file inside .husky folder
