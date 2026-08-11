# ALK — hero redesign (deploy)

Cztery samodzielne pliki HTML. Bez podfolderów, bez build stepu — wszystkie style,
fonty, skrypty design systemu i obrazy są zaszyte w każdym pliku.

| Plik               | Widok                       |
| ------------------ | --------------------------- |
| `index.html`       | Strona główna — desktop      |
| `mobile.html`      | Strona główna — mobile       |
| `login.html`       | Wybór strefy — desktop       |
| `login-mobile.html`| Wybór strefy — mobile        |

Linki między stronami są względne (`login.html` itd.), więc działają w każdym katalogu.

## Git

```
git init
git add .
git commit -m "ALK hero redesign"
git remote add origin <adres-repo>
git push -u origin main
```

## Vercel

Repo podpięte w Vercel deployuje się bez konfiguracji — to statyczne HTML.
Framework preset: **Other**. Build command: puste. Output directory: `.`
`index.html` jest stroną startową.

Alternatywnie z CLI:

```
npx vercel deploy --prod
```
