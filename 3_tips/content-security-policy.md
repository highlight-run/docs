---
title: Content-Security-Policy
slug: 9pQt-content-security-policy
createdAt: 2022-03-01T00:39:25.000Z
updatedAt: 2022-03-01T01:08:28.000Z
---

```hint
You should keep reading this if your application runs in an environment that enforces content security policies.
```

`Content-Security-Policy` allows you to tell the browser what and how your page can interact with third-party scripts.

Here are the policies you'll need to set to use Highlight:

1.  `script-src`: `https://static.highlight.io https://unpkg.com/web-vitals/dist/web-vitals.iife.js`

    1.  This policy is to allow downloading the Highlight runtime code for session recording and error monitoring, as well as the unpkg web vitals reporting bundle used by Highlight.
    2.  If you are using a [version of highlight.run < 5.0](https://www.npmjs.com/package/highlight.run/v/5.0.0), change the domain `static.highlight.io` to `static.highlight.run`.

2.  `connect-src`: `https://pub.highlight.run`
    1.  This policy is to allow connecting with Highlight servers to receive recorded session data.
3.  `worker-src`: `blob:`
    1. This policy allows our script to start a web-worker which we use to serialize the recording data without affecting the performance of your application.

Your [CSP](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP) definition may look something like this:

```html
<meta
	http-equiv="Content-Security-Policy"
	content="default-src 'self'; script-src 'self' https://static.highlight.io https://unpkg.com/web-vitals/dist/web-vitals.iife.js; connect-src https://pub.highlight.run; worker-src blob:"
/>
```
