# `git push` tricks
#git

## `git push` to different remote branch

```bash
git push origin local-name:remote-name
```

and when force is neccesary

```bash
git push --force-with-lease origin local-name:remote-name
```

`force-with-lease` ensures remote work is not overwritten.