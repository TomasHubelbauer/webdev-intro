# WebDev Intro

- https://nodejs.org/en/download: install NodeJS and add it to %PATH%
  - Or: https://github.com/coreybutler/nvm-windows/releases to add `nvm` to %PATH%
  - `nvm` allows switching `node` (and `npm` versions on the same machine)
  - `nvm install latest` downloads and installs latest Node and matching NPM
  - `nvm use 14.3.0` switches Node and NPM to the given version
  - `node -v` to check Node version
  - `npm -v` to check NPM version
- `npm i -g create-react-app`: install globally - not in the repository
  - `npx create-react-app  --help`
  - NPX comes with NPM and executes binary packages on-the-fly
  - Good for one-off utilities or to ensure latest version is being used
  - Example of binary package: https://github.com/tomashubelbauer/shoot
- `create-react-app fe --template typescript`
  - HMR - hot module reloading - save to preview changes
- `cd fe`
- `npm start`
- https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi
- https://chrome.google.com/webstore/detail/redux-devtools/lmhkpmbekcpmknklioeibfkpmmfibljd
- Ctrl+P go to file by name
- Ctrl+T go to symbol
- Ctrl+Shift+P to list/search VS Code commands
- https://github.com/timarney/react-app-rewired to avoid `eject` if possible
- `proxy` field in `package.json` to point 404ing resources to a proxy URL
  - Good for backend: FE is localhost:3000, BE & proxy is localhost:5000
- SASS support: `npm i node-sass` and then `import` SCSS files like CSS files
  - Developer Command Prompt for Visual Studio - C compiler
  - `npm rebuild node-sass`
- CSSOM, BEM for maintaining isolated stylesheets
  - Also check out `styled-components` and other CSS in JS solutions
- UI component sets:
  - https://github.com/react-bootstrap/react-bootstrap
  - https://github.com/microsoft/fluentui
- Forms: Redux-Form, Formik, …
- Escape hatches: `useRef`, `__dangerouslySetInnerHTML`
- Modals & dialogs: check out React portals
- View models: type union `{ state: 'pending', … } | { state: 'completed', … }`

```ts
switch (state.type) {
  case 'pending': {
    // Type here is { state: 'pending' }
  }
  case 'complete': {
    // Type here is { state: 'pending' }
  }
  case 'failed': {
    // Return portal…
  }
}
```

```tsx
render() {
  return (
    <div>
      <h1>Heading</h1>
      {isError && React.createPortal(<p>An error occured!</p>, document.getElementById('modal'))}
    </div>
  )
}
```
