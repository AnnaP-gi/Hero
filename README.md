# ALK — makieta Ciemna 2 (desktop + mobile)

Statyczne, samodzielne pliki HTML. Każdy plik zawiera wszystkie zasoby w środku — nie wymaga budowania.

## Strony

| Plik | Widok |
| --- | --- |
| `index.html` | Strona główna — Ciemna 2 (desktop) |
| `mobile.html` | Strona główna — ciemna (mobile) |
| `search.html` | Wyniki wyszukiwania (desktop) |
| `search-mobile.html` | Wyniki wyszukiwania (mobile) |
| `login.html` | Zaloguj się (desktop) |
| `login-mobile.html` | Zaloguj się (mobile) |

## Rozpoznawanie urządzenia

Każda strona ma skrypt, który przy wejściu sprawdza urządzenie (user agent + szerokość < 820 px)
i w razie potrzeby przekierowuje do odpowiednika: `index.html` ↔ `mobile.html`,
`search.html` ↔ `search-mobile.html`, `login.html` ↔ `login-mobile.html`.

Decyzja opiera się na user agencie i `screen.width` (< 820 px = mobile) — nie na szerokości okna,
żeby meta viewport poszczególnych makiet nie powodowała pętli przekierowań. Dodatkowo obowiązuje
limit jednego przekierowania na sesję (`sessionStorage: alk-nr`).

Wymuszenie widoku: `?view=desktop` albo `?view=mobile` (zapamiętywane w localStorage).
Reset wymuszenia: wyczyść localStorage klucz `alk-view`.

## Uwaga

Na stronie wyników pasek nawigacji jest statyczny (linki działają, mega menu nie rozwija się).

## Przejścia

- Logo w nagłówku → strona główna
- Zaloguj się → `login.html`
- SZUKAJ w wyszukiwarce → `search.html`

## Deployment

Vercel: `vercel deploy --prod` w tym katalogu (albo import repo z GitHuba — bez ustawień budowania,
katalog wyjściowy = katalog projektu).
