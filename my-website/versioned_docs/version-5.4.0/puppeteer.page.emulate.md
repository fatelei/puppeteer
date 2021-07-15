<!-- Do not edit this file. It is automatically generated by API Documenter. -->

[Home](./index.md) &gt; [puppeteer](./puppeteer.md) &gt; [Page](./puppeteer.page.md) &gt; [emulate](./puppeteer.page.emulate.md)

## Page.emulate() method

Emulates given device metrics and user agent. This method is a shortcut for calling two methods:  and  To aid emulation, Puppeteer provides a list of device descriptors that can be obtained via the  `page.emulate` will resize the page. A lot of websites don't expect phones to change size, so you should emulate before navigating to the page.

<b>Signature:</b>

```typescript
emulate(options: {
        viewport: Viewport;
        userAgent: string;
    }): Promise<void>;
```

## Parameters

|  Parameter | Type | Description |
|  --- | --- | --- |
|  options | { viewport: [Viewport](./puppeteer.viewport.md); userAgent: string; } |  |

<b>Returns:</b>

Promise&lt;void&gt;

## Remarks

List of all available devices is available in the source code: [src/common/DeviceDescriptors.ts](https://github.com/puppeteer/puppeteer/blob/main/src/common/DeviceDescriptors.ts).

## Example


```js
const puppeteer = require('puppeteer');
const iPhone = puppeteer.devices['iPhone 6'];
(async () => {
const browser = await puppeteer.launch();
const page = await browser.newPage();
await page.emulate(iPhone);
await page.goto('https://www.google.com');
// other actions...
await browser.close();
})();

```
