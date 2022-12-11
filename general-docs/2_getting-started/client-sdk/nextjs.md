---
title: Next.js
slug: d3G0-nextjs
createdAt: 2021-09-13T23:00:33.000Z
updatedAt: 2022-10-18T23:54:07.000Z
---

```hint
For a more comprehensive tour of our client sdk, visit our [client reference page](docs/sdk/client).
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
import type { AppProps } from 'next/app'
import { H } from 'highlight.run'
import { ErrorBoundary } from '@highlight-run/react'

H.init('<YOUR_PROJECT_ID>') // Get your project ID from https://app.highlight.run/setup

function MyApp({ Component, pageProps }: AppProps) {
	return (
		<ErrorBoundary>
			<Component {...pageProps} />
		</ErrorBoundary>
	)
}
export default MyApp
```

## Verify

Start your app, go to it in the browser, then click around. Highlight will be recording your session and it will show up on <https://app.highlight.run/sessions> a few seconds after recording has started.

## Next Steps

After installing Highlight for your frontend application, there are a few other things you should check out about our Session Replay product, namely:
-- [Privacy Controls](/docs/session-replay/privacy)
-- [Network Request Recording](/docs/session-replay/recording-network-requests-and-responses)
-- [Backend Setup Guides](/docs/getting-started/backend-sdk/overview)