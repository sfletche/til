Today I accidentally closed the terminal window 
which resulted in the following error when attempting to restart my local dev server:

`Error: listen EADDRINUSE`

Normally, when there's a problem with my local dev server it's because there are processes still running that need to be killed.

Easy enough.  My usual strategy is to just look at the existinr process and kill off the relevant ones...

**Did Not Work**

```
ps
kill -9 <pid>
```

But this time, `ps` showed no such processes.  (I'm guessing because the process in question had become orphaned, but I'm guessing)

After a gazillion posts on stackoverflow gave me nothing that worked, I finally found 
[one answer|http://stackoverflow.com/a/30163868/379512] suggesting [`lsof`|https://en.wikipedia.org/wiki/lsof] 
to list all open files belonging to all active processes (with `-i` to ignore the device cache file, and `tcp:` to identify the local port number).  


**Success!**

```
lsof -i tcp:<port num>
kill -9 <pid>
```

Viola.  Process identified and destroyed.  :)

**EDIT**: alternatively (and possibly easier to remember) `lsof | grep <port num>`
