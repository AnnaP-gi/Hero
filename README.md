# ALK — hero redesign (deploy)

Statyczny build gotowy pod Git i Vercel. Wszystko w jednym folderze, bez podfolderów
i bez build stepu — style, fonty, skrypty i obrazy są zaszyte w każdym pliku HTML.

| Plik                  | Widok                                  |
| --------------------- | -------------------------------------- |
| `index.html`          | Desktop — **jasny** (strona startowa)  |
| `ciemny-1.html`       | Desktop — **ciemny 1**                 |
| `ciemny-2.html`       | Desktop — **ciemny 2**                 |
| `mobile.html`         | Mobile — jasny                         |
| `mobile-ciemny.html`  | Mobile — ciemny                        |
| `login.html`          | Wybór strefy — desktop                 |
| `login-mobile.html`   | Wybór strefy — mobile                  |

## Przełączanie widoków

Na desktopie w dolnej części ekranu jest przełącznik **Jasny / Ciemny 1 / Ciemny 2**.
Wybór zapisuje się w `localStorage` (`alk-view` + `alk-theme`) i steruje tym,
którą wersję mobilną zobaczy użytkownik.

## Rozpoznawanie urządzenia

Każdy plik przy wejściu sprawdza szerokość ekranu i typ wskaźnika. Telefon =
szerokość poniżej 900px albo ekran dotykowy poniżej 1000px.

- Telefon + zapamiętany widok **jasny** (lub brak wyboru) → `mobile.html`
- Telefon + zapamiętany widok **ciemny 1 lub ciemny 2** → `mobile-ciemny.html`
- Desktop wchodzący na adres mobilny → wraca na ostatnio wybraną wersję desktopową
- Strefa logowania przełącza się między `login.html` a `login-mobile.html`

Wejście wprost na `ciemny-1.html` z telefonu też zapisuje motyw ciemny i pokazuje
mobilną ciemną — czyli link do dowolnej ciemnej wersji desktopowej otwiera na
telefonie ciemny mobile.

Żeby obejrzeć konkretny plik niezależnie od urządzenia, dodaj `?noswitch`
do adresu, np. `…/ciemny-2.html?noswitch`.

Widoki mają stałą szerokość projektową (1440px i 390px) ustawioną w `<meta viewport>`,
więc na telefonie strona skaluje się do szerokości ekranu zamiast wystawać poza kadr.

## Git

```
git init
git add .
git commit -m "ALK hero redesign"
git branch -M main
git remote add origin <adres-repo>
git push -u origin main
```

## Vercel

Repo podpięte w Vercel deployuje się bez konfiguracji — to statyczne HTML.
Framework preset: **Other**, Build command: puste, Output directory: `.`
`index.html` jest stroną startową. Plik `vercel.json` ustawia tylko czyste
adresy (`/ciemny-1` zamiast `/ciemny-1.html`).

Z CLI:

```
npx vercel deploy --prod
```
