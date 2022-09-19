# Astro Github Time Element

This is a astro wrapper for the [@github/time-elements](https://github.com/github/time-elements) library, it does a few things:

- Makes importing components is easier
- Ability to use `Date` objects with the `datetime` prop
- Adds typing to props
- `<LocalTime>`: creates it own date object by default
- Small API for adding attributes 

## How to Use

```
npm i astro-github-time-elements
```

```ts

---
import LocalTime from 'astro-github-time-elements';
---

<LocalTime date time/>
```

**Output**:
```
<local-time 
    datetime="2022-09-19T00:49:24.526Z"
    year="numeric"
    month="short"
    day="numeric"
    hour="2-digit"
    minute="2-digit"
    second="2-digit"
    title="Sep 18, 2022, 7:49 PM CDT"
>
    Sep 18, 2022 07:49:24 PM
</local-time>
```

## Extended API

[Check out the @github/time-elements API](https://github.com/github/time-elements) to see how these components work, below are a few props added by this wrapper to make using the components a little bit easier

### `datetime`

**Type**: `Date | string`

Wrapper gives ability to use a `Date` for all components `datetime` prop

### `<LocalTime>`

#### `datetime`

**Default**: `new Date`

If no `datetime` is defined for a `<LocalTime>` component it creates its own

#### `date`

**Type**: `booelan`

A formating preset used to easily show a date without having to type out a format, adds the following attributes:

```tsx
year="numeric"
month="short"
day="numeric"
```

**Example**:

```tsx
<LocalTime date/> // Sep 18, 2022
```

#### `time`

**Type**: `booelan`

A formatting preset used to easily show a time without having to type out a format, adds the following attributes:

```tsx
hour="2-digit"
minute="2-digit"
second="2-digit"
```

**Example**:

```tsx
<LocalTime time/> // 07:49:24 PM
```

### `<TimeUntil> && <TimeAgo>`

#### `micro`

**Type**: `booelan`

Adds the attribute `format="micro"` to your element, shortens the descriptions to 1m, 1h, 1d, 1y

**Example**: 

```tsx
<TimeUntil datetime="2023-01-01T00:00:00.000Z"> // 'in 3 months'
<TimeUntil micro datetime="2023-01-01T00:00:00.000Z"> // '104d'
```

## More Examples

```tsx
<LocalTime date/> // Sep 18, 2022
<LocalTime time/> // 09:40:34 PM
<LocalTime date time/> // Sep 18, 2022 09:40:34 PM
<RelativeTime datetime="2022-09-17T00:00:00.000Z" /> // 2 days ago
<TimeUntil datetime="2023-01-01T00:00:00.000Z"/> // in 3 months
<TimeUntil micro datetime="2023-01-01T00:00:00.000Z"/> // 104d
<TimeAgo datetime="2020-01-01T00:00:00.000Z"/> // 3 years ago
<TimeAgo micro datetime="2020-01-01T00:00:00.000Z"/> // 3y
```

[Check out the @github/time-elements API](https://github.com/github/time-elements) for more help