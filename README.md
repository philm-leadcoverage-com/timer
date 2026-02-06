# Timer Widget

A simple, embeddable countdown/countup timer that displays time in a clean, readable format.

## Features

- **Countdown Mode**: Count down to a future date
- **Count Up Mode**: Count up from a past date
- **Flexible Display**: Show or hide seconds
- **Clean Design**: Minimal 400px × 100px frame
- **URL-Configured**: All settings via query parameters

## Usage

### Countdown Timer

Count down to a specific date and time:

```
timer.html?to_date=2025-12-31-23-59-59
```

### Count Up Timer

Count up from a specific date and time:

```
timer.html?from_date=2024-01-01-00-00-00
```

### Show/Hide Seconds

Add `show_seconds=TRUE` to display seconds (hidden by default):

```
timer.html?to_date=2025-12-31-23-59-59&show_seconds=TRUE
```

## Date Format

Dates must be in the format: `YYYY-MM-DD-HH-MM-SS`

- **YYYY**: 4-digit year (e.g., 2025)
- **MM**: 2-digit month (01-12)
- **DD**: 2-digit day (01-31)
- **HH**: 2-digit hour (00-23)
- **MM**: 2-digit minute (00-59)
- **SS**: 2-digit second (00-59)

### Examples

- New Year 2026: `2026-01-01-00-00-00`
- Christmas 2025: `2025-12-25-09-00-00`
- Birthday (June 15, 2025 at 3:30 PM): `2025-06-15-15-30-00`

## Display Format

The timer displays time in this format:

```
[X years, Y months, Z days, ]HH:MM[:SS]
```

- Years, months, and days only show if non-zero
- Hours always show (00-∞)
- Minutes always show (00-59)
- Seconds show only if `show_seconds=TRUE` (00-59)

### Examples

- `2 years, 3 months, 15 days, 4:23:17`
- `5 days, 12:08:45`
- `0:45:30`
- `156:22` (with `show_seconds=FALSE`)

## Behavior

### Countdown Mode (`to_date`)
- Shows time remaining until the target date
- When the date is reached, displays `0:00:00` (or `0:00` without seconds)
- Useful for: deadlines, launches, events

### Count Up Mode (`from_date`)
- Shows time elapsed since the start date
- If the date is in the future, displays `0:00:00` until reached
- Useful for: anniversaries, project duration, uptime

## Embedding

The timer is designed as a 400px × 100px widget. Embed it using an iframe:

```html
<iframe 
  src="timer.html?to_date=2025-12-31-23-59-59&show_seconds=TRUE"
  width="400" 
  height="100" 
  frameborder="0">
</iframe>
```

## Styling

The timer uses a card-based design with:
- Light gray background (#f7f7f7)
- Soft shadow for depth
- System font for readability
- Responsive text sizing

## Requirements

- Modern web browser with JavaScript enabled
- No external dependencies
- No server-side processing required

## Error Handling

If the date parameter is missing or invalid, the timer displays:
```
Timer error: [description]
```

Common errors:
- `Missing to_date or from_date` - No date parameter provided
- `Bad date format` - Date doesn't match YYYY-MM-DD-HH-MM-SS format
- `Invalid date` - Date values are out of range (e.g., month 13)
## License

This project is licensed under the GNU General Public License v3.0 (GPL-3.0).

You are free to use, modify, and distribute this software, but any derivative works must also be licensed under GPL-3.0 and made open source.

See [LICENSE](LICENSE) for full details.
