# Note
I didn't yet receive the template repository for the project yet, so I'm putting my post here until I receive it.
I also do have some prior experience utilizing GitHub on a different account which is more of a "personal" account rather than a professional one (I have some of my own public repositories with actual code).

# Tags
overflow, 32-bit, time computing 

# Overview
The Year 2038 problem is a vulnerability in legacy 32-bit systems that store time. In order to determine what time it is, instead of storing the current year, month, and day, instead they store the number of seconds that have passed since the Unix epoch, which is an arbitrary date set to January 1st, 1970. The ability to tell time is essential for institutions like banks which need to calculate interest someone accrues in their account over a specific period of time. However, a 32-bit signed integer (which is what the legacy Unix timestamp standard currently uses) can only store numbers from -2,147,483,648 to 2,147,483,647. As it just so occurs, exactly 2,147,483,647 seconds since January 1st, 1970 falls on January 19th, 2038. And on that date, if systems are left unchanged, the timer will experience an overflow and "time travel" all the way back to December 13th, 1901. This is a time discrepancy of about 136 years from the real time and the reported time after the bug occurs.

# Purpose
This blog seeks to dive deeper into the issue, compare existing solutions to the issue, and provide a full technical explanation as to how this bug occurs and what can be done regarding it. A full technical breakdown of the issue will be made, explaining exactly why it happens.

# Sources
- https://theyear2038problem.com/
- https://www.kaspersky.com/blog/mitigating-y2k38-vulnerability-in-organization/55150/
- https://en.wikipedia.org/wiki/Year_2038_problem
