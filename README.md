# Devspace examples

This repo shows a devspace example project with git dependencies, with the same dependency (`postgres`) being referenced multiple times (by both the root project, the `app` dependency, and the `app2` dependency):

- root project
  - app
    - postgres
    - app2
      - postgres
