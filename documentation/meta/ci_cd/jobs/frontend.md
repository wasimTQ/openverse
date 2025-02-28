# Frontend jobs

## `nuxt-build`

```{note}
This job is treated as the proof of functionality for publishing Docker images
for the frotend.

This job, combined with the [`playwright` job](#playwright), is treated as the
proof of functionality for deploying frontend to staging.
```

## `nuxt-checks`

Runs a matrix for various Nuxt checks for the frontend using the following
Node.js scripts.

- `test:unit`
- `storybook:smoke`

This job is skipped if the frontend codebase has not changed. Its counterpart is
[`django-checks`](#django-checks) for the API.

Since this is a required check for a matrix job, it has a bypass counterpart.
Refer to the documentation for [bypass jobs](#bypass-jobs).

## `playwright`

Runs a matrix of various Playwright tests for the frontend using the following
Node.js scripts.

- `test:playwright visual-regression`
- `test:playwright e2e`
- `test:storybook`

This job is skipped if the frontend codebase has not changed.

```{note}
This job, combined with the [`nuxt-build` job](#nuxt-build), is treated as the
proof of functionality for deploying frontend to staging.
```

Since this is a required check for a matrix job, it has a bypass counterpart.
Refer to the documentation for [bypass jobs](#bypass-jobs).
