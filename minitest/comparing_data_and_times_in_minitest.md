# Comparing dates and times in minitest

Ruby and rails has quite a few class to represent dates and times. It can be hard to compare them directly since rules and behaviors are complicated in comparisons and coercing types. A better approach is to compare their string representations.

When writing test in a rails project, It's better to:

- Get current time with `Time.zone.now`
- Convert standard ruby `Time` and `DateTime` object to `TimeWithZone` equivalents using the `in_time_zone` method.
- Avoid error in precision by comparing String representation.
- Using rails's `to_formatted_s` method as a shortcut to get standardized representations of times and dates

## Reference

- [Minitest cookbook], p80

[Minitest cookbook]: http://chriskottom.com/minitestcookbook/
