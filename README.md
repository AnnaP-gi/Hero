# ALK — makieta Ciemna 2 (desktop + mobile)

Statyczne, samodzielne pliki HTML. Wszystkie zasoby (fonty, obrazy, skrypty) są w środku — nie
wymagają budowania ani połączenia z zewnętrznymi serwerami.

Wygenerowane: 9 września 2026. Zawiera wyłącznie wersję **Ciemną 2** (desktop) i jej ciemny odpowiednik mobilny.

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

Domyślny jest **desktop**. Na wersję mobilną przenoszą się wyłącznie urządzenia mobilne
rozpoznane po user agencie (Android / iPhone / iPod / IEMobile / Opera Mini oraz iPad w trybie
desktop-UA rozpoznawany po dotyku i szerokości ekranu). Szerokość okna przeglądarki nie ma
znaczenia — wąskie okno na desktopie nie przełącza widoku.

Obowiązuje limit jednego przekierowania na sesję (`sessionStorage: alk-nr`), więc pętle nie występują.
Wymuszenie widoku: `?view=desktop` albo `?view=mobile` (zapamiętywane w `localStorage`, klucz
`alk-view` — wyczyść, aby wrócić do automatu).

## Menu i belka rekrutacyjna

- Górne menu (logo + zakładki + mega menu) jest **sticky na każdej stronie**
- Niebieska belka rekrutacyjna jest **zamykalna (X)** i nie jest przypięta — na stronie głównej
  i na wynikach wyszukiwania
- Na stronie logowania belki **nie ma**
- Logo → strona główna, Zaloguj się → `login.html`, SZUKAJ → `search.html`

## Deployment

Vercel: `vercel deploy --prod` w tym katalogu (albo import repo z GitHuba — bez ustawień budowania,
Framework Preset = Other, katalog wyjściowy = katalog projektu).

GitHub: wystarczy wrzucić zawartość tego katalogu do repozytorium (można też włączyć GitHub Pages
z katalogu głównego — `index.html` jest stroną startową).
