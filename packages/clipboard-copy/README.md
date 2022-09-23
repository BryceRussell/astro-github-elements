# `@astro-github-elements/clipboard-copy`

This is a astro wrapper for the [@github/clipboard-copy-element](https://github.com/github/clipboard-copy-element#readme) component, it does a few things:

- Makes importing component easier
- Adds typing to props

## How to Use

```
npm i @astro-github-elements/clipboard-copy
```

```tsx

---
import { LocalTime } from '@astro-github-elements/time';
---

<ClipboardCopy value="copy me">Click me</ClipboardCopy>
```

**Output**:
```
<clipboard-copy value="copy me">Click me</clipboard-copy>
```

## API

You can find the API for this component here: [@github/clipboard-copy-element](https://github.com/github/clipboard-copy-element#readme)

## Todo

- Add styling presets?
- Show how to use with rehype?