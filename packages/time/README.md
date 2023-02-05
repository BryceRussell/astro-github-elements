# `@astro-github-elements/time`

This is a astro wrapper for the [@github/relative-time-element](https://github.com/github/relative-time-element#readme) library, it does a few things:

- Makes importing and using web component is easier
- Adds typing to props
- Ability to use `Date` objects with the `datetime` prop
- Pass current time using `now` prop

# Why?

This component lets the client decide how to render the date for more accessibility

## How to Use

```
npm i @astro-github-elements/time
```

```jsx

---
import { Time } from '@astro-github-elements/time';
---

<Time format="datetime" now />
<Time format="datetime" datetime="2022-09-19T00:49:24.526Z" />

<Time format="relative" now />
<Time format="relative" datetime="2022-09-19T00:49:24.526Z" />
```

**Output**:
```html
<relative-time datetime="2023-02-05T17:19:08.898Z" format="datetime" title="Feb 5, 2023, 11:19 AM CST">
  Sun, Feb 5
</relative-time>

<relative-time datetime="2022-09-19T00:49:24.526Z" format="datetime" title="Sep 18, 2022, 7:49 PM CDT">
  Sun, Sep 18, 2022
</relative-time>

<relative-time datetime="2023-02-05T17:20:43.371Z" format="relative" title="Feb 5, 2023, 11:20 AM CST">
  now
</relative-time>

<relative-time datetime="2022-09-19T00:49:24.526Z" format="relative" title="Sep 18, 2022, 7:49 PM CDT">
  on Sep 18, 2022
</relative-time>
```

## Changes to API

The full API for this component can be viewed here: [@github/relative-time-element](https://github.com/github/relative-time-element#readme)

Below are a few tiny changes

### `format`

Format is required instead of defaulting to `relative`, this is so that there is only one component named `<Time>`

### `datetime`

The datetime prop can be either a Date or ISO string

This also means the `date` attribute is not included in props because it is redundant and is mostly for client side JavaScript

### `now`

A new prop, shorthand for doing `datetime={new Date}`, do not use with the `datetime` prop
