# In order to setup a _Next.js_ app with _Typescript_, _ESLint_, _Prettier_, _Husky_ and also setting a _Git_ Repository, We have to follow these steps below

## Git

- At first, We should delete every Git file using: `rd .git /s/q`
- Then we must initialize our Git in our Project using: `git init`
- Add every single changed files to your Repository: `git add .`
- Commit your changes on your Repository with: `git commit -m ""`
- Create a new Repository on the Github website
- Set the existing Git Repository with your Project using: `git remote add origin GIT_REP_ADDRESS`
- Push all the changes with: `git push -u origin master`
- You can see the content of a proper .gitignore file in here <https://github.com/Danielkhakbaz/Danial-Portfolio-Hub/blob/main/.gitignore>

## ESLint

- Add ESLint to your Project: `yarn add eslint`
- Start initializing ESLint for your Project: `yarn run eslint --init`
- This is the .eslintrc.json I used for my projects, I provide you the link so you can use it for your projects <https://github.com/Danielkhakbaz/Danial-Portfolio-Hub/blob/main/.eslintrc.json>
- You can see the content of a proper .eslintignore in here <https://github.com/Danielkhakbaz/Danial-Portfolio-Hub/blob/main/.eslintignore>
- Add the "next" and "prettier" in the end of all the extends in the .eslintrc.json file

## Prettier

- Add Prettier to your Project: `yarn add prettier`
- Then add "prettier" to your .eslintrc file as one of the extends
- Install this package for the solving the conflict between ESLint and Prettier using: `yarn add eslint-config-prettier && yarn add eslint-config-next`
- Create a .prettierrc file and start writing your rules as a json
- Suggested rules are:
  `{
  "printWidth": 80,
  "tabWidth": 2,
  "semi": true,
  "singleQuote": false,
  "bracketSpacing": true,
  "bracketSameLine": false,
  "trailingComma": "es5",
  "endOfLine": "lf"
}
`
- You can see the content of a proper .prettierignore in here <https://github.com/Danielkhakbaz/Danial-Portfolio-Hub/blob/main/.prettierignore>

## Next.js

- My go-to next.config.js is in here <https://github.com/Danielkhakbaz/Danial-Portfolio-Hub/blob/main/next.config.js>

## Typescript

- My go-to tsconfig.json is in here <https://github.com/Danielkhakbaz/Danial-Portfolio-Hub/blob/main/tsconfig.json>

## VSCode

- Set your default formatter on VSCode to Prettier - Code Formatter
- Then turn on the FormatOnSave and FormatOnPaste on your settings
- Create a new Folder named .vscode
- Inside that, Create a settings.json
- Start writing these codes as json in the settings.json file:
  `  "editor.formatOnPaste": true,
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": "explicit",
    "source.fixAll.format": "explicit"
  }`

## Husky

- Install husky on your Project: `npx husky-init && yarn`
- Add these lines of scripts to your package.json file:
  ` "dev": "next dev",
    "build": "next build",
    "start": "next start",
    "fix": "next lint --fix && prettier --write .",
    "lint": "next lint",
    "upgrade": "upgrade-interactive --latest",
    "knip": "npx knip",
    "analyze": "ANALYZE=true yarn build",
    "postinstall": "husky install && prisma generate"`
- Add these texts from <https://github.com/Danielkhakbaz/Danial-Portfolio-Hub/blob/main/.husky/pre-commit> to pre-commit file inside .husky folder
- Just in case You're using yarn instead of npm, You should pay attention to the pre-commit file
