# Site location

https://thelaluka.github.io/CabinetOsteopathieDutertre/

## Test locally

```bash
rm resources docs ; ./hugo serve -D -b http://localhost/
```

## Publish

```bash
rm resources docs ; ./hugo -b https://osteo-vigny-dutertre.fr/
git status
git add .; git commit -m "I dit foo in bar"; git push
```
