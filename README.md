# branch_migration

At `main` branch:
```bash
cat meow > cat.txt
git add .
git commit
git push -u origin main
```

Create `neko` branch and switch to it:
```bash
git switch -c neko
cat nya > neko.txt
git add .
git commit
git push -u origin neko
```

Now `neko` is 1 commit ahead.

Back up main:
```bash
git branch -m main old-main
```

On `neko`, rename `neko` to `main` and push it as a new `main`:
```bash
git branch -m neko main
git push -u origin main
```

The last `git push` replaces the new `main`(renamed from `neko`) to remote `main` without further operations.

