# branch_migration

From `e36d06b` at `main` branch in this repogitory:
```bash
echo meow2 > cat.txt
git add .
git commit
git push
```

Create `neko` branch and switch to it:
```bash
git switch neko
echo meowmeow > cat.txt
git add .
git commit
git push
```

Now `neko` is not fast-forward to `main`; there is a conflict in `cat.txt`.

Back up main:
```bash
git branch -m main old-main
git push -u origin old-main
```

Force push `neko` overwriting `main`.
c.f. [git-push](https://git-scm.com/docs/git-push#Documentation/git-push.txt-codegitpushorigindevmastercode)
```bash
git push origin +neko:main
git fetch
git switch main
```

After checking `main` is a desired state, delete branches.

