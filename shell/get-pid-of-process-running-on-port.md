Today I accidentally closed the terminal window 
which resulted in the following error when attempting to restart my local dev server:

`Error: listen EADDRINUSE`

Normally, when there's a problem with my local dev server it's because there are processes still running that need to be killed.

Easy enough.  My usual strategy is to just look at the existinr process and kill off the relevant ones...

`ps`
`kill -9 <pid>`

But this time, `ps` showed no such processes.  (I'm guessing because the process in question had become orphaned, but I'm guessing)

After a gazillion posts on stackoverflow gave me nothing that worked, I finally found 
[one answer|http://stackoverflow.com/a/30163868/379512] suggesting [`lsof`|https://en.wikipedia.org/wiki/Lsof].

`lsof -i tcp:<port num>`
`kill -9 <pid>`

Viola.  Process identified and destroyed.  :)
