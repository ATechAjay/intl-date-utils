
# intl-date-utils

Lightweight date utilities powered by the modern JavaScript Intl API.

Features:

- Zero dependencies
- Intl based formatting
- Timezone aware
- Relative time utilities
- Small bundle size
- Works in Node.js and modern browsers

## Installation

npm install intl-date-utils

## Usage

```js
import { formatDate, timeAgo } from 'intl-date-utils'

formatDate(new Date())
timeAgo(new Date(Date.now() - 86400000))
```

## Available Methods

| Method | Description | Example |
|------|-------------|--------|
| `formatDate(date, locale?, style?)` | Formats a date using locale-aware Intl date styles (`full`, `long`, `medium`, `short`). | `formatDate(new Date(), "en-US", "long")` |
| `formatTime(date, locale?, style?)` | Formats only the time portion of a date using Intl time styles. | `formatTime(new Date(), "en-US")` |
| `formatDateTime(date, locale?, options?)` | Formats date and time together with optional timezone support. | `formatDateTime(new Date(), "en-US", { timeZone: "Asia/Tokyo" })` |
| `formatInTimezone(date, timeZone, locale?)` | Formats a date in a specific timezone regardless of system timezone. | `formatInTimezone(new Date(), "Asia/Tokyo")` |
| `toLocaleDateISO(date, timeZone?)` | Returns a timezone-aware ISO calendar date string (`YYYY-MM-DD`). Useful for comparing dates across timezones. | `toLocaleDateISO(new Date(), "UTC")` |
| `timeAgo(date, locale?)` | Returns human-readable relative time like "3 days ago" or "in 2 hours". | `timeAgo(new Date(Date.now() - 86400000))` |
| `getMonthNames(locale?, style?)` | Returns an array of localized month names. | `getMonthNames("en-US")` |
| `getDayNames(locale?, style?, startDay?)` | Returns localized weekday names with optional start day (0 = Sunday, 1 = Monday). | `getDayNames("en-US", "long", 1)` |
| `formatRange(start, end, locale?, style?)` | Formats a date range using Intl range formatting. | `formatRange(new Date("2026-03-10"), new Date("2026-03-15"))` |
| `isToday(date)` | Returns `true` if the provided date is today. | `isToday(new Date())` |
| `isYesterday(date)` | Returns `true` if the date is yesterday. | `isYesterday(new Date(Date.now() - 86400000))` |
| `isTomorrow(date)` | Returns `true` if the date is tomorrow. | `isTomorrow(addDays(new Date(), 1))` |
| `startOfDay(date)` | Returns a new Date representing the start of the day (00:00:00). | `startOfDay(new Date())` |
| `endOfDay(date)` | Returns a new Date representing the end of the day (23:59:59.999). | `endOfDay(new Date())` |
| `addDays(date, amount)` | Adds or subtracts days from a date. | `addDays(new Date(), 5)` |
| `addMonths(date, amount)` | Adds or subtracts months from a date. | `addMonths(new Date(), 2)` |
| `differenceInDays(a, b)` | Returns the number of calendar days between two dates. | `differenceInDays(new Date("2026-03-15"), new Date("2026-03-10"))` |
| `parseISO(value)` | Parses an ISO date string and returns a Date object with validation. | `parseISO("2026-03-15")` |
| `formatSmartDate(date, locale?)` | Smart UI formatting (Today, Yesterday, relative time, or formatted date). | `formatSmartDate(new Date())` |

## Development

Install dependencies

```bash
npm install
```

Run tests

```bash
npm test
```

Build library

```bash
npm run build
```

## Test Package Locally

Create npm tarball

```bash
npm pack
```

This generates:

```bash
intl-date-utils-1.0.0.tgz
```

You can test install locally:

```bash
npm install ./intl-date-utils-1.0.0.tgz
```

## Publish to npm

Login

```bash
npm login
```

Publish

```bash
npm publish --access public
```

## License

MIT
