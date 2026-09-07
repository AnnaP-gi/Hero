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

Wymuszenie widoku: `?view=desktop` albo `?view=mobile` (zapamiętywane w localStorage).

## Przejścia

- Logo w nagłówku → strona główna
- Zaloguj się → `login.html`
- SZUKAJ w wyszukiwarce → `search.html`

## Deployment

Vercel: `vercel deploy --prod` w tym katalogu (albo import repo z GitHuba — bez ustawień budowania,
katalog wyjściowy = katalog projektu).
