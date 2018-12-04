Recently I started using `git log --pretty=format` to list a set of commits.

This works really when when the dev process includes Squash and Merge strategy (single commit for each merge of a feature branch),
and you want a nice way to view the commits between tags (e.g. between the last deploy and the current deploy).

```
git log  --pretty=format:"%h - %an - %s"  devploy-v1.0.0..deploy-v1.0.1
```
