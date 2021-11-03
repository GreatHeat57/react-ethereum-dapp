
## Installation

Download the latest verion of Parity [here](https://github.com/paritytech/parity/releases).

Also ensure that you have the latest verion of Truffle installed globally:

```bash
npm install -g truffle
```

Finally install all package dependencies:

```bash
npm install
```

## Running Dev Environment

Run all of the following commands inside the project directory.

### 1) Start Parity Development Chain

```bash
parity --chain dev --ws-origins "*"
```

Note: we set `--ws-origins` so that we can use websockets to subscribe to blockchain events.

### 2) Compile and Migrate smart-contracts

```bash
truffle compile && truffle migrate
```

NOTE: after running open parity (at [`http://127.0.0.1:8180/`](http://127.0.0.1:8180/)) in a browser and confirm all of the transactions to complete the migration.

### 3) Start Dev Javascript Server

```bash
npm run dev
```

The first time it may take a little while to generate the first `webpack-assets.json` and complain with a few dozen `[webpack-isomorphic-tools] (waiting for the first Webpack build to finish)` printouts, but be patient. Give it 30 seconds.

You're good to go! :) Now you can access the dapp at: [`http://localhost:3000`](http://localhost:3000).

#### Using Redux DevTools

[Redux Devtools](https://github.com/gaearon/redux-devtools) are enabled by default in development.

- <kbd>CTRL</kbd>+<kbd>H</kbd> Toggle DevTools Dock
- <kbd>CTRL</kbd>+<kbd>Q</kbd> Move DevTools Dock Position
- see [redux-devtools-dock-monitor](https://github.com/gaearon/redux-devtools-dock-monitor) for more detailed information.

If you have the [Redux DevTools chrome extension](https://chrome.google.com/webstore/detail/redux-devtools/lmhkpmbekcpmknklioeibfkpmmfibljd) installed it will automatically be used on the client-side instead.

If you want to disable the dev tools during development, set `__DEVTOOLS__` to `false` in `/webpack/dev.config.js`.  
DevTools are not enabled during production by default.
