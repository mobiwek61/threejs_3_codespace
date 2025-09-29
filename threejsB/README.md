bb
## cd to folder threejsB to begin!!!
## my notes 
- this is a github codespace project.
- About auto reload. Parcel(setup by codesandbox) and Vite(setup with unix commands in codespace) are both development servers which auto reload and cause browser to refresh, BUT Parcel gets tripped up in codespace because of port forwarding. Thats why vite is used here.
- Run below commands to setup vite in codespace (very easy)  
  make git repo named threejs_3b and do a codespace from it. You now have a unix box with a terminal appearing in browser window.  
  from (copilot recommended) run: 
```
npm create vite@latest three3b -- --template react-ts
cd three3b
npm i three
npm run dev
```
- browser window pops up with app in it. To get app in ide window, "ports" (on bottom) then mouseover it and click "open in browser". It autorefreshes!   

### Problem: you commit on github webpage and try to commit from codespace   
- you get incomprehensible github error.
- Fix: type into copilot "in github I edit a file then open a codespace and when I commit and push codespace a git error occurs". Then it says to:
```
git config pull.rebase false
git pull
```
Then merge errors. copilot says to:   
```Open the Conflicted File In Codespaces, open threejsB/README.md. You’ll see conflict markers like:```
Then push the merge button, then commit+push.
- To compare 2 commits in github webpage: 
```https://github.com/username/repo/compare/commit1..commit2```  
  Commit 1 and 2 are the SHA codes shown in history button on github webpage for the file.

**=========================================================
=========================================================**
### README created by: <br>`npm create vite@latest three3b -- --template react-ts`

# React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## React Compiler

The React Compiler is not enabled on this template because of its impact on dev & build performances. To add it, see [this documentation](https://react.dev/learn/react-compiler/installation).

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type-aware lint rules:

```js
export default defineConfig([
  globalIgnores(['dist']),
  {
    files: ['**/*.{ts,tsx}'],
    extends: [
      // Other configs...

      // Remove tseslint.configs.recommended and replace with this
      tseslint.configs.recommendedTypeChecked,
      // Alternatively, use this for stricter rules
      tseslint.configs.strictTypeChecked,
      // Optionally, add this for stylistic rules
      tseslint.configs.stylisticTypeChecked,

      // Other configs...
    ],
    languageOptions: {
      parserOptions: {
        project: ['./tsconfig.node.json', './tsconfig.app.json'],
        tsconfigRootDir: import.meta.dirname,
      },
      // other options...
    },
  },
])
```

You can also install [eslint-plugin-react-x](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-x) and [eslint-plugin-react-dom](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-dom) for React-specific lint rules:

```js
// eslint.config.js
import reactX from 'eslint-plugin-react-x'
import reactDom from 'eslint-plugin-react-dom'

export default defineConfig([
  globalIgnores(['dist']),
  {
    files: ['**/*.{ts,tsx}'],
    extends: [
      // Other configs...
      // Enable lint rules for React
      reactX.configs['recommended-typescript'],
      // Enable lint rules for React DOM
      reactDom.configs.recommended,
    ],
    languageOptions: {
      parserOptions: {
        project: ['./tsconfig.node.json', './tsconfig.app.json'],
        tsconfigRootDir: import.meta.dirname,
      },
      // other options...
    },
  },
])
```