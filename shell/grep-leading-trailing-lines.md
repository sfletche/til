Today I learned how to limit the leading and/or trailing lines surrounding a `grep` search...

`grep -A5` include five trailing lines of context after each match

`grep -B5` include five leading lines of context after each match

`grep -C5` include five trailing and five leading lines of context after each match
