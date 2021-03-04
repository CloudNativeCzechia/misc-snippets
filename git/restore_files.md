# Restore state of repository
#git

## Delete everything and return to last commited state

```bash
git reset --hard
```

## Restore to last commited state but leave files 

```bash
git reset --soft
```

## Repair, Split existing commit

```bash
git rebase -i <some commit in history that is old enough>
# edit the commit I want to work on
git reset HEAD~
# work as needed, commit multiple times
git rebase --continue
```

## Reset multiple commits back

Reset the commits and leave the files in working directory. Usefull for fixing commit tree.

```bash
git reset <commit id to the point of reset, one before the commit to be reseted>
```