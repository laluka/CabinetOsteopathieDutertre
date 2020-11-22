# Test locally

```bash
hugo serve -D -b http://localhost/
```

# Publish

```bash
rm resources docs
hugo -D
git status
git add foo bar
git commit -m "I dit foo in bar"
git push
```