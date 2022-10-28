---
title: H.metrics()
slug: F65Z-hmetrics
createdAt: 2022-10-03T19:34:32.000Z
updatedAt: 2022-10-18T23:23:34.000Z
---

This method is used to submit custom metrics. You can learn more about [Frontend Observability.](/product-features/frontend-observability)

```typescript
H.metrics(metrics: Metric[]) => void;
```

## `metrics` _(Metrics\[])_ Required

A list of metrics that you'd like to report. Check out [Metrics](/api/client/h-metrics)

### Example

```typescript
H.metrics([{
	name: 'clicks',
	value: 1,
	tags: [{ browser }]
}, {
	name: 'auth_time',
	value: authDelay,
	tags: [{ version: 'v2' }]
}
```

## `name` _(string)_

The name of the metric you are reporting.

## `value` _(number)_

The numeric value of the metric.

## `tags` _({ name: string; value: string }\[])_

A set of name,value pairs the represent tags about the metric. Tags can be used to filter and group metrics. See [Frontend Observability](/product-features/frontend-observability) for more details.
