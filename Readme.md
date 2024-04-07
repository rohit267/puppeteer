# Puppeteer Docker

Simple `puppeteer` docker image to run your scripts in a headless browser.

## Features:

- Puppeteer v22.6.3
- Node.js v18
- Chrome

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=rohit267/puppeteer&type=Timeline)](https://star-history.com/#rohit267/puppeteer&Timeline)

## Usage:

Make a script.js file with your puppeteer code.

```js
const puppeteer = require("puppeteer");

(async () => {
  const browser = await puppeteer.launch();
  const page = await browser.newPage();
  await page.goto("https://example.com");
  await page.screenshot({ path: "example.png" });
  console.log("Screenshot taken");
  await browser.close();
})();
```

### Docker Compose

```yaml
version: "3"

services:
  puppeteer:
    image: ghcr.io/rohit267/puppeteer
    volumes:
      - /home/homeserver/currentDocker/script.js:/app/script.js
    cap_add:
      - SYS_ADMIN
```
