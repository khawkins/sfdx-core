## Contributing

1. The [DEVELOPING](DEVELOPING.md) doc has details on how to set up your environment.
1. Familiarize yourself with the codebase by reading the [docs](docs), which you can generate locally by running `yarn docs`.
1. Create a new issue before starting your project so that we can keep track of
   what you are trying to add/fix. That way, we can also offer suggestions or
   let you know if there is already an effort in progress.
1. Fork this repository.
1. Create a _topic_ branch in your fork based on the correct branch (usually the **develop** branch, see [Branches section](#branches) below). Note, this step is recommended but technically not required if contributing using a fork.
1. Edit the code in your fork.
1. Write appropriate tests for your changes. Try to achieve at least 95% code coverage on any new code. No pull request will be accepted without unit tests.
1. Sign CLA (see [CLA](#cla) below).
1. Send us a pull request when you are done. We'll review your code, suggest any
   needed changes, and merge it in.

### CLA

External contributors will be required to sign a Contributor's License
Agreement. You can do so by going to https://cla.salesforce.com/sign-cla.

## Branches

- We work in `develop`.
- Our released (aka. _production_) branch is `master`.
- Our work happens in _topic_ branches (feature and/or bug-fix).
  - feature as well as bug-fix branches are based on `develop`
  - branches _should_ be kept up-to-date using `rebase`
  - [commit messages are enforced](DEVELOPING.md#When-you-are-ready-to-commit)
  - see below for further merge instructions

### Merging between branches

- We try to limit merge commits as much as possible.

  - They are usually only ok when done by our release automation.

- _Topic_ branches are:

  1. based on `develop` and will be
  1. squash-merged into `develop`.

- Hot-fix branches are an exception.
  - Instead we aim for faster cycles, and a generally stable `develop` branch.

### Merging `develop` into `master`

- When a development cycle finishes, the content of the `develop` branch will become the `master` branch

```
$ git checkout master
$ git reset --hard develop
$
$ # Using a custom commit message for the merge below
$ git merge -m 'Merge -s our (where _ours_ is develop) releasing stream x.y.z.' -s ours origin/master
$ git push origin master
```

## Pull Requests

- Develop features and bug fixes in _topic_ branches.
- _Topic_ branches can live in forks (external contributors) or within this repository (committers).  
  \*\* When creating _topic_ branches in this repository please prefix with `<developer-name>/`.

### Merging Pull Requests

- Pull request merging is restricted to squash & merge only.
