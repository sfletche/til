Today I learned the spread operator is actually implemented / specified in 2 different versions of ECMAScript.

A recent conversation at the office.

    Me: 'I thought the spread operator was part of ES6.'
    Other Dev: 'It is'
    Me: 'Then why is the linter complaining?  And why are my unit tests failing?'
    Other Dev: 'I don't know.  Spread operator was working for me yesterday.'
    Me: :-/

So it turns out while **Array Spread Operator is part of ES6/ES2015**, the Object Spread Operator is not. 

The **Object Spread Operator is a Stage 2 Proposal for ECMAScript**, and so (while widely used thanks to transpilers), is not currently part of the spec.

Needless to say, this prompted some Babel / Linter library updates.  Of which I'll try and talk about in tomorrow's til...
