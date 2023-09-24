## Git hooks and husky

- Install configuration packages in your devDependencies

  ```bash
  yarn add -D @commitlint/cli @commitlint/config-conventional husky lint-staged validate-branch-name
  ```

- We need to add some configuration to a file named `commitlint.config.js` like this:

  ```js
  module.exports = {
    extends: ['@commitlint/config-conventional'],
    rules: {
      'type-enum': [
        2,
        'always',
        [
          'build',
          'chore',
          'ci',
          'docs',
          'feat',
          'fix',
          'perf',
          'refactor',
          'revert',
          'style',
          'test',
          'button',
          'docker',
        ],
      ],
    },
  };
  ```

- We also need to enable the husky hooks:

  ```sh
    yarn husky install
  ```

  - Finally, let's set up lint-staged in the `package.json` file so that it runs Prettier on JS files:

    ```json
    {
      "scripts": {
        "prepare": "husky install"
      },
      "lint-staged": {
        "**/*.{ts,tsx}": ["prettier --write --ignore-unknown", "eslint --fix"]
      }
    }
    ```

  - Now that we are done installing husky

    - we need to add a pre-commit hook to run before the code is committed.

      ```sh
      yarn husky add .husky/commit-msg "yarn commitlint --edit $1"
      yarn husky add .husky/pre-commit "yarn validate-branch-name"
      yarn husky add .husky/pre-commit "yarn lint-staged"
      ```

    - we need to add a pre-push hook to run before the code is pushed.

      ```sh
      yarn husky add .husky/pre-push "yarn build"
      ```

###### Git commit message

> feat, fix, docs, style, refactor, test, chore, perf, ci, build and temp.

| Type     | Description                                                                                             |
| -------- | ------------------------------------------------------------------------------------------------------- |
| feat     | A new feature.                                                                                          |
| fix      | A bug fix.                                                                                              |
| docs     | Documentation only changes.                                                                             |
| style    | Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc). |
| refactor | A code change that neither fixes a bug nor adds a feature.                                              |
| test     | Adding missing tests or correcting existing ones.                                                       |
| chore    | Changes to the build process or auxiliary tools and libraries such as documentation generation.         |
| perf     | A code change that improves performance.                                                                |
| ci       | Changes to your CI configuration files and scripts.                                                     |
| build    | Changes that affect the build system or external dependencies (example scopes: gulp, broccoli, npm).    |
| temp     | Temporary commit that won't be included in your CHANGELOG.                                              |

- scope:
  Optional, can be anything specifying the scope of the commit change.
  For example $location, $browser, $compile, $rootScope, ngHref, ngClick, ngView, etc.  
   In App Development, scope can be a page, a module or a component.

- subject:
  Brief summary of the change in present tense. Not capitalized. No period at the end.

###### Skipping Hooks

In the terminal, you can bypass hooks by adding the --no-verify option, like in this example:

```sh
git commit -m "skipping hooks" --no-verify
```
