---
title: React.js Quickstart
slug: reactjs
createdAt: 2021-09-13T22:48:34.000Z
updatedAt: 2022-05-26T17:21:00.000Z
---

```hint
Reference our [client-side sdk docs](/docs/sdk/client) for advanced functionality and our [fullstack mapping guide](/docs/getting-started/frontend-backend-mapping) on pairing backend errors with your replay.
```
# Installing the SDK

Install `highlight.run` and `@highlight-run/react` using your package manager.

```shell
# with npm
npm install highlight.run @highlight-run/react

# with yarn
yarn add highlight.run @highlight-run/react
```

## Initialize

Initialize Highlight where your application starts.

```typescript
import { H } from 'highlight.run'

H.init(
	'<YOUR_PROJECT_ID>', // Get your project ID from https://app.highlight.run/setup
)
```

### Example

```typescript
import React from 'react'
import { H } from 'highlight.run'
import { ErrorBoundary } from '@highlight-run/react'

H.init('<YOUR_PROJECT_ID>') // Get your project ID from https://app.highlight.run/setup

ReactDOM.render(
	<React.StrictMode>
		<ErrorBoundary>
			<App />
		</ErrorBoundary>
	</React.StrictMode>,
	document.getElementById('root'),
)
```

# A react-specific package

In addition to `highlight.run`, Highlight ships [`@highlight-run/react`](https://github.com/highlight-run/react) which can be installed alongside `highlight.run` for additional functionality for React applications, namely the `<ErrorBoundary/>`. Read more about it [here](getting-started/client-sdk/reactjs/error-boundary).


## Verify

Start your app, go to it in the browser, then click around. Highlight will be recording your session and it will show up on <https://app.highlight.run/sessions> a few seconds after recording has started.
