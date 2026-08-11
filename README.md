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

## Automatyczne przełączanie desktop / mobile

Każdy plik sprawdza przy wejściu szerokość ekranu i typ wskaźnika:
poniżej 900px (albo ekran dotykowy poniżej 1000px) `index.html` przekierowuje na
`mobile.html`, a `login.html` na `login-mobile.html`. W drugą stronę: wersje mobilne
na ekranie ≥1000px bez dotyku wracają na desktopową.

Żeby zobaczyć konkretną wersję niezależnie od urządzenia, dodaj `?noswitch` do adresu,
np. `…/index.html?noswitch`.

Widoki mają stałą szerokość projektową (1440px i 390px) ustawioną w `<meta viewport>`,
więc na telefonie strona skaluje się do szerokości ekranu zamiast wystawać poza kadr.

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
