A long time ago I learned about robots.txt and, it seems, promptly forgot about it.
Today I was reminded...

[Web crawlers](https://en.wikipedia.org/wiki/Web_crawler) are what search engines use to index the world wide web.
The resulting index can then be used to respond to web searches.  

A [`robots.txt`](https://en.wikipedia.org/wiki/Robots_exclusion_standard) file can be used to indicate which paths/files/etc the web crawlers should ignore.

For example, the following specifies that all user agents (all web crawlers) should ignore everything on this site...
```
User-agent: *
Disallow: /
```

And the following specifies that all user agents can index all the pages they want...
```
User-agent: *
Disallow: 
```



