# Next.js + Pino

Use [pino](https://github.com/pinojs/pino) on server and client side in Next.js project 

## Installation

```bash
npm install --save pino next-pino
```

or 

```bash
yarn add pino next-pino
```

## Usage

Create a `next.config.js` in your project

```js
// next.config.js
const withPino = require("next-pino");
module.exports = withConfig();
```

Create a logger file `utils/logger/JsonLogger.js`

```js
import pino from "pino";

export default pino()({
  // usual pino config
});
```

Then you could use it on another file, for example

```js
import JsonLogger from "utils/logger/JsonLogger.js";

JsonLogger.info("foo bar");
```

### Configuring Next.js

Optionally you can add your custom Next.js configuration as parameter

```js
// next.config.js
const withPino = require("next-pino");
module.exports = withConfig({
  webpack(config, options) {
    return config;
  }
});
```