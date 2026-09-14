# ALK — makieta Ciemna 2 (desktop)

Trzy samodzielne pliki HTML. Wszystkie zasoby — fonty, obrazy, logotypy akredytacji i rankingów,
skrypty — są wbudowane w środku. Żadnych podfolderów, żadnego budowania.

| Plik | Widok |
| --- | --- |
| `index.html` | Strona główna |
| `search.html` | Wyniki wyszukiwania |
| `login.html` | Zaloguj się |

Linki: logo → `index.html`, „Zaloguj się" → `login.html`, „SZUKAJ" → `search.html`.

## Usuń `vercel.json` z repozytorium

To najpewniejsza przyczyna obecnego 404. Poprzednia wersja tego pliku zawierała
`"outputDirectory": "."`, co przy projekcie bez budowania każe Vercelowi szukać katalogu
wyjściowego zamiast po prostu podać pliki — i kończy się `404: NOT_FOUND`.

Repozytorium z samymi plikami HTML w katalogu głównym nie potrzebuje żadnej konfiguracji.
Na GitHubie: otwórz `vercel.json` → ikona kosza → Commit changes. Vercel przebuduje sam.

## Jeśli 404 zostanie

1. **Ustawienia projektu.** Panel Vercela → Settings → Build and Deployment.
   Framework Preset = **Other**, Build Command, Output Directory i Install Command — puste
   (przełączniki „Override" wyłączone). Root Directory puste
2. **Log wdrożenia.** Deployments → wybierz najnowsze → sprawdź, czy status to Ready.
   Jeśli Error, w logu widać przyczynę
3. **Rozmiar plików.** Mają po 9–11 MB. Jeśli GitHub przy którymś pokazuje
   „Stored with Git LFS", Vercel dostanie wskaźnik zamiast pliku. Wgrywaj przez
   Add file → Upload files, nie przez klienta z włączonym LFS
4. **Cache przeglądarki.** Otwórz adres w trybie prywatnym

## Porządki w repozytorium (opcjonalnie)

Pliki `ciemny-1.html`, `ciemny-2.html`, `mobile-ciemny.html`, `mobile.html`,
`search-mobile.html`, `login-mobile.html` to poprzednie wersje. Nie przeszkadzają, ale można
je usunąć — aktualne są tylko `index.html`, `search.html` i `login.html`.

## Test rozstrzygający

Otwórz `index.html` dwuklikiem z dysku. Jeśli działa lokalnie, a nie po wgraniu, przyczyna
leży w konfiguracji Vercela — nie w plikach.
