Today I learned about the [Rollbar grouping algorithm](https://rollbar.com/docs/grouping-algorithm/) 
and why it's gonna be a problem for tracking JS errors.

Rollbar error grouping is by Occurrences which can either be 
* Exceptions (which contain an Exception Class, Exception Message, and a Stack Trace), or
* Messages (string message)

For exceptions (including JS errors), the basic grouping algorithm is as follows...
* combine filenames and method names from stack frames
* append exception class name, environment, and platform
* take SHA1 of hash of result

The problem is then for uglified/minified files (at least until we have actual source maps), 
the method names will differ after each and every build.

This means that any changes to reported errors (Muting/Resolving/or Adjusting Error Levels) will only last until the next build,
after which they will simply surface again.

:(



