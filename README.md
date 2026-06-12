# Cabinet d'Ostéopathie Aurélie Dutertre

Site vitrine du cabinet d'ostéopathie d'Aurélie Dutertre (Grenoble, quartier Vigny-Musset).

- **Production** : https://osteo-vigny-dutertre.fr/ (domaine custom via `static/CNAME`)
- **Hébergement** : GitHub Pages, qui sert le dossier `docs/` commité sur `main`
- **Générateur** : [Hugo](https://gohugo.io/) v0.68.3 extended — binaire commité à la racine (`./hugo`), aucune installation requise
- **Thème** : [hargo-hugo-ecommerce-theme](https://github.com/themefisher/hargo-hugo-ecommerce-theme) (vendored dans `themes/`)

## Structure

```
config.toml                # menus, coordonnées, réseaux sociaux, copyright
data/homepage.yml          # contenu de l'accueil (hero, parcours, cartes, engagement)
data/contact.yml           # bloc "nous situer" / horaires de la page contact
content/                   # pages : osteopathie-docu, osteopathie-tarifs, smartboard, liens-utiles, contact
layouts/index.html         # override du template d'accueil (layout zen : hero / photo+parcours / cartes / citation)
layouts/partials/head.html # override SEO : canonical, Open Graph, twitter card, JSON-LD MedicalBusiness
static/custom.css          # @font-face Telegraf + style 2026 (fond "papier" + halos, accent terracotta)
static/fonts/              # Telegraf woff auto-hébergées (200/400/800)
static/images/             # images du site (max 1600px, jpeg qualité 82)
themes/.../_variables.scss # couleurs du thème ($primary-color terracotta, polices)
docs/                      # site généré, servi par GitHub Pages — ne pas éditer à la main
```

## Tester en local

```bash
rm -rf resources && ./hugo serve -D -b http://localhost/
# → http://localhost:1313/
```

## Publier

```bash
rm -rf resources docs && ./hugo -b https://osteo-vigny-dutertre.fr/
git add . && git commit -m "description du changement" && git push
```

GitHub Pages redéploie automatiquement après le push (~1 min).

## Conventions

- **Images** : redimensionner à 1600px max et compresser avant d'ajouter
  (`magick img.jpg -resize '1600x1600>' img.jpg && jpegoptim -m82 --strip-all img.jpg`),
  avec un attribut `alt` descriptif en français.
- **Police** : Telegraf auto-hébergée (`static/fonts/`), fallback Quicksand ;
  déclarée dans `static/custom.css` et `$primary-font` du thème.
- **Couleurs** : accent terracotta `#C2603E` défini dans `themes/.../_variables.scss`
  et dans les variables CSS de `static/custom.css` (`--accent`).
