Today I learned about pre-commit hooks in Git.  

I used the [npm library `pre-commit`](https://www.npmjs.com/package/pre-commit) 
to run our linting process before every commit (can I get a Hell Yeah???).

If there are linting issues (that can't be auto-fixed) the commit is blocked until the issues are addressed.

And of course you can still force the commit to happen, by including the `--no-verify` argument.  

Configuration takes place within your `package.json`.  And mine looks something like this...

```
  "scripts": {
    "eslint": "eslint --config path/to/lint/config/file --fix path/to/my/lintable/files --ext .js,.jsx --cache",
    "lint-staged": "lint-staged"
  },
  "pre-commit": [
    "lint-staged"
  ],
  "lint-staged": {
    "*.{js,jsx}": ["eslint", "git add"]
  }
```

The above configuration tells the `pre-commit` library to perform the `lint-staged` script whenever a commit is performed
(before the commit is executed).

The `lint-staged` script is defined in the `lint-staged` object and basically says, whenever a `.js` or `.jsx` file is included 
in the commit, perform the `eslint` script defined above, and run `git add` after that. 

The reason we run `git add` is we've included `--fix` in the eslint command and that flag causes all auto-fixable linting errors
to be fixed automagically, and we want those changes to be staged for the commit.

If the `eslint` command fails (because linting errors remain), the commit will be blocked.

If the `eslint` command succeeds (no linting errors, either before or after the auto-fixes), the commit will execute.

Finally, if you wish to bypass the `pre-commit` script altogether you can add `--no-verify` to the `git commit` call.
