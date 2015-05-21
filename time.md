---
tagline: time and sleeping
platforms: mingw, linux, osx
---

## `local time = require'time'`

## API

------------------------- ----------------------------------------------------
`time.time() -> t`        wall clock time with ~100us precision
`time.clock() -> k`       monotonic time in seconds with ~1us precision
`time.sleep(s)`           sleep with sub-second precision (~10-100ms)
------------------------- ----------------------------------------------------

## Notes

`time.time()` times are UNIX timestamps and are compatible with `os.time()`
times on all platforms. They read the wall-clock time and are thus
affected by drifting, leap seconds and time adjustments by the user.
They are not affected by timezones. They can be used to synchronize time
between different boxes on a network regardless of platform.

`time.clock()` times are more accurate, never go back or drift,
but they don't have a fixed time base between program executions.
They can be used for measuring short time intervals.
