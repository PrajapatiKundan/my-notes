# Git naming conventions

## Branch naming conventions

1. Use grouping tokens (words) at the beginning of your branch names.
2. Define and use short lead tokens to differentiate branches in a way that is meaningful to your workflow.
3. Use slashes to separate parts of your branch names.
4. Do not use bare numbers as leading parts.
5. Avoid long descriptive names for long-lived branches.

### Short well-defined tokens

`wip` Works in progress; stuff I know won't be finished soon

`feat` Feature I'm adding or expanding

`bug` Bug fix or experiment

`junk` Throwaway branch created to experiment

Examples,

```
feat/delete-item

fix/css-for-mediaItem-comp
```

### Find branches

`git branch --list "feat/*"`: List all feature branches

## Git Commit message conventions

1. Use following tokens

feat: A new feature

fix: A bug fix

style: Additions or modifications related to styling only

refactor: Code refactoring

test: Additions or modifications to test cases

docs: README, Architectural, or anything related to documentation

chore: Regular code maintenance

2. Start commit message with capitol letter

3. Do not end message with full-stop

4. The first word in your commit message should be one of these:

Add
Create
Refactor
Fix
Release
Document
Modify
Update
Remove
Delete etc...

Example,

```
git commit -m "feat: Add mediaItem component"
```

## References

[Git naming convention](https://stackoverflow.com/questions/273695/what-are-some-examples-of-commonly-used-practices-for-naming-git-branches)
