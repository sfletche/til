After experiencing a hiccup in which one of our node dependencies updated in a non-semver manner and subsequently broke our build, 
we decided to lock down our package versions.  

So rather than using the semver range operator, `^` ("Compatible with version"), we decided that our dependencies should 
match the version specified.  

Today I learned that there's even a `--save-exact` option on `npm install` that will configure the dependency with an exact version
(rather than the default semver range operator applied when using `--save` on its own).

`npm install <package-name> --save --save-exact`
