---
title: React Error Boundary
slug: react-error-boundary
createdAt: 2021-09-13T22:48:34.000Z
updatedAt: 2022-05-26T17:21:00.000Z
---


# A react-specific package

In addition to `highlight.run`, Highlight ships [`@highlight-run/react`](https://github.com/highlight-run/react) which can be installed alongside `highlight.run` for additional functionality for React applications, namely the `<ErrorBoundary/>`.

## Installing the SDK

Install `highlight.run` and `@highlight-run/react` using your package manager.

```shell
# with npm
npm install highlight.run @highlight-run/react

# with yarn
yarn add highlight.run @highlight-run/react
```

```hint
Have you integrated the `highlight.run` package into your React app yet using `H.init()`? If not, follow the instructions [here](/getting-started/client-sdk/reactjs) first.
```

# React Error Boundary

This react-specific package provides an `ErrorBoundary` to help you provide a better experience for your users when your application crashes. Using an `ErrorBoundary` gives your application an opportunity to recover from a bad state.

Highlight also allows you to show a crash report powered by [User Feedback](/product-features/user-feedback). A crash report is shown in the session when the crash happens, giving you the context for the user feedback.

```typescript
import { ErrorBoundary } from '@highlight-run/react'

const App = () => (
	<ErrorBoundary showDialog>
		<YourAwesomeApplication />
	</ErrorBoundary>
)
```

## Examples

### Showing the feedback modal when a crash happens

![](https://archbee-image-uploads.s3.amazonaws.com/XPwQFz8tul7ogqGkmtA0y/2VUVTR1ot591xUfJZSc3m_2022-01-1213-17.png)

```typescript
import { ErrorBoundary } from '@highlight-run/react'

const App = () => (
	<ErrorBoundary showDialog>
		<YourAwesomeApplication />
	</ErrorBoundary>
)
```

### Showing a custom feedback modal when a crash happens

You should use this if you would like to replace the feedback modal with your own styles/branding.

```typescript
import { ErrorBoundary } from '@highlight-run/react'

const App = () => (
	<ErrorBoundary
		showDialog
		customDialog={
			<div>
				<h2>Whoops! Looks like a crash happened.</h2>
				<p>Don't worry, our team is tracking this down!</p>

				<form>
					<label>
						Feedback
						<input type="text" />
					</label>

					<button type="submit">Send Feedback</button>
				</form>
			</div>
		}
	>
		<YourAwesomeApplication />
	</ErrorBoundary>
)
```

## ErrorBoundary API

### `fallback`

A fallback component that gets rendered when the error boundary encounters an error.

## `showDialog`

Enables Highlight's crash report. When the `ErrorBoundary` is triggered, a form will be prompted to the user asking them for optional feedback.

### `dialogOptions`

The strings used for the Highlight crash report.

`user`

Allows you to attach additional user information to the feedback report. If you've called [`H.identify()`](/sdk/client#Hidentify) in your application before, you won't have to set this, Highlight will infer the user's identity.

`title`

The title for the report dialog.

`subtitle`

The subtitle for the report dialog.

`subtitle2`

The secondary subtitle for the report dialog.

`labelName`

The label for the name field.

`labelEmail`

The label for the email field.

`labelComments`

The label for the verbatim field.

`labelClose`

The label for the close button.

`labelSubmit`

The label for the submit button.

`successMessage`

The label for the success message shown after the crash report is submitted.

`hideHighlightBranding`

Whether to show the Highlight branding attribution in the report dialog.

Default value is `false`.