# Devspace examples

This repo shows a devspace example project with git dependencies, with the same dependency (`redis`) being referenced multiple times (by both the root project and the `app` dependency):

- root project
  - app
    - redis
  - nginx
  - redis

Since `redis` is added as a dependency with identical parameters (git source, same branch, same variables etc.), I would have expected it to be cloned, built and deployed only once. As of `devspace v5.18.1` this is not the case:

The project is cloned multiple times, once per git dependency; this can add up quite a bit when working with larger git repos and a dependency tree with 25+ nodes.

```
❯ devspace update dependencies
[done] √ Pulled git@github.com:bforchhammer/devspace-dependency-example
[done] √ Pulled git@github.com:bforchhammer/devspace-dependency-example
[done] √ Pulled git@github.com:bforchhammer/devspace-dependency-example
[done] √ Successfully updated all dependencies
```
