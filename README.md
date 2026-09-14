# ALK — makieta Ciemna 2 (desktop)

Trzy samodzielne pliki HTML. Wszystkie zasoby — fonty, obrazy, logotypy akredytacji i rankingów,
skrypty — są wbudowane w środku. Żadnych podfolderów, żadnego budowania.

## Pliki

| Plik | Widok |
| --- | --- |
| `index.html` | Strona główna |
| `search.html` | Wyniki wyszukiwania |
| `login.html` | Zaloguj się |
| `vercel.json` | Konfiguracja (opcjonalna) |

Linki między stronami: logo → `index.html`, „Zaloguj się" → `login.html`, „SZUKAJ" → `search.html`.
Nazwy plików są użyte dosłownie, więc działają też przy otwarciu z dysku — wystarczy kliknąć
dwukrotnie `index.html`.

## Wgranie na Vercel — najprostsza droga

1. Wejdź na **vercel.com/new**
2. Przeciągnij na stronę te trzy pliki HTML (lub cały rozpakowany folder)
3. Framework Preset: **Other**. Nie wpisuj polecenia budowania ani katalogu wyjściowego
4. Deploy

Przez CLI: `vercel deploy --prod` uruchomione **w katalogu z tymi plikami**.

## Jeśli pojawia się 404: NOT_FOUND

Najczęstsze przyczyny, w kolejności prawdopodobieństwa:

1. **Wgrany został sam folder, nie jego zawartość.** Wtedy strony leżą pod
   `/deploy/index.html`, a nie pod `/`. W panelu Vercela: Settings → Build and Deployment →
   Root Directory → wskaż `deploy` (albo wgraj ponownie samą zawartość folderu)
2. **Brakuje pliku.** 404 na `/search.html` oznacza, że wgrany został tylko `index.html`.
   Wszystkie trzy pliki muszą leżeć obok siebie
3. **Adres wpisany ręcznie.** Otwórz adres główny (`https://nazwa.vercel.app`), nie podstronę
4. **Nieudany build.** Zakładka Deployments → wybierz wdrożenie → Building. Jeśli Vercel próbuje
   cokolwiek budować, usuń ustawienia budowania (Framework Preset = Other, puste pola)

## vercel.json

Zawiera tylko odwołanie do schematu — konfiguracja nie jest potrzebna, bo to zwykłe pliki
statyczne. Plik można usunąć bez żadnych konsekwencji.
