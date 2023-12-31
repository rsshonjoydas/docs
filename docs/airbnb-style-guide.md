Airbnb style guide setup

- Install those packages in devDependencies

  ```bash
  yarn add -D @next/eslint-plugin-next @typescript-eslint/eslint-plugin @typescript-eslint/parser eslint-config-airbnb eslint-config-prettier eslint-plugin-import eslint-plugin-jsx-a11y eslint-plugin-react eslint-plugin-react-hooks prettier prettier-plugin-tailwindcss
  ```

- We need to add some configuration to a file named `.eslintrc.json` like this:

  ```json
  {
    "env": {
      "browser": true,
      "es2021": true
    },
    "extends": ["plugin:@next/next/recommended", "airbnb", "prettier"],
    "globals": {
      "React": "readonly"
    },
    "parser": "@typescript-eslint/parser",
    "parserOptions": {
      "ecmaFeatures": {
        "jsx": true,
        "tsx": true
      },
      "ecmaVersion": "latest",
      "sourceType": "module"
    },
    "plugins": ["react", "@typescript-eslint"],
    "rules": {
      "no-console": "off",
      "react/react-in-jsx-scope": "off",
      "react/state-in-constructor": "off",
      "jsx-a11y/click-events-have-key-events": "off",
      "react/prop-types": "off",
      "import/no-extraneous-dependencies": "off",
      "indent": "off",
      "linebreak-style": "off",
      "react/function-component-definition": "off",
      "react/jsx-props-no-spreading": "off",
      "no-plusplus": "off",
      "jsx-a11y/no-redundant-roles": "off",
      "jsx-a11y/anchor-is-valid": "off",
      "jsx-a11y/label-has-associated-control": "off",
      "jsx-a11y/no-static-element-interactions": "off",
      "import/extensions": "off",
      "import/no-unresolved": "off",
      "react/no-danger": "off",
      "import/prefer-default-export": "off",
      "jsx-a11y/no-noninteractive-element-interactions": "off",
      "react/jsx-filename-extension": [1, { "extensions": [".ts", ".tsx"] }],
      "react/require-default-props": "off",
      "no-nested-ternary": "off",
      "no-unused-vars": "error"
    }
  }
  ```

- We need to add some configuration to a file named `.prettierrc` like this:

  ```json
  {
    "plugins": ["prettier-plugin-tailwindcss"],
    "trailingComma": "es5",
    "singleQuote": true,
    "jsxSingleQuote": true,
    "printWidth": 100,
    "tabWidth": 2,
    "semi": true,
    "endOfLine": "auto"
  }
  ```

- We need to add some configuration to a file named `.prettierignore` like this:
  ```sh
  .yarn
  yarn.lock
  .github
  .next
  next-env.d.ts
  out
  dist
  public
  node_modules
  ```
