Add this json code by creating `settings.json` inside the `.vscode` folder in your project root directory.

```json
{
  //TODO: checkTheme
  "workbench.colorTheme": "Atom One Dark",
  //TODO: config related to code formatting
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.formatOnSave": true,
  "[javascript]": {
    "editor.formatOnSave": true,
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "[javascriptreact]": {
    "editor.formatOnSave": true
  },
  "javascript.validate.enable": false, //* disable all built-in syntax checking
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true,
    "source.fixAll.tslint": true,
    "source.organizeImports": true
  },
  "eslint.alwaysShowStatus": true,
  //TODO: emmet
  "emmet.triggerExpansionOnTab": true,
  "emmet.includeLanguages": {
    "javascript": "javascriptreact"
  },
  "css.validate": false,
  "scss.validate": false,
  "tailwindCSS.emmetCompletions": true,
  "tailwindCSS.includeLanguages": {
    "plaintext": "html",
    "javascript": "javascript"
  },
  "editor.quickSuggestions": {
    "other": true,
    "comments": true,
    "strings": true
  },
  "tailwindCSS.classAttributes": ["class", "className", "ngClass"],
  "typescript.tsdk": "node_modules\\typescript\\lib",
  "typescript.enablePromptUseWorkspaceTsdk": true,
  "cSpell.userWords": ["shonjoy", "rsshonjoy", "rsshonjoydas"]
}
```
