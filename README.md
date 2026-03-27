# CV Jekyll Site (Estelle Takaoka)

Ce projet est un site CV statique généré avec **Jekyll**.

## Prérequis
- Ruby (>= 3.0)
- Bundler

## Installation
```powershell
cd c:\Users\estel\Downloads\Github
bundle install
```

## Exécution locale
```powershell
bundle exec jekyll serve --host 0.0.0.0 --port 4000
```

Accéder ensuite à `http://localhost:4000`.

## Structure
- `index.md` : template Front Matter + inclusion du contenu CV
- `_layouts/default.html` : markup global HTML
- `_data/cv.yml` : données du CV
- `assets/css/style.css` : styles
