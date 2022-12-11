---
title: React.js
slug: reactjs
createdAt: 2021-09-13T22:48:34.000Z
updatedAt: 2022-05-26T17:21:00.000Z
---

```hint
For a more comprehensive tour of our client sdk for React.js, visit our [client reference page](docs/sdk/client).
```

## Installing the SDK

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

## Verify

Start your app, go to it in the browser, then click around. Highlight will be recording your session and it will show up on <https://app.highlight.run/sessions> a few seconds after recording has started.

## Configuration

Learn more about the other developer experience goodies Highlight provides by seeing [React.js](/getting-started/client-sdk/reactjs).

## Next Steps

After installing Highlight for your frontend application, there are a few other things you should check out about our Session Replay product, namely:
-- [Privacy Controls](/docs/session-replay/privacy)
-- [Network Request Recording](/docs/session-replay/recording-network-requests-and-responses)
-- [Backend Setup Guides](/docs/getting-started/backend-sdk/overview)