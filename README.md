# Analiza piłkarska

Startowa aplikacja webowa po polsku. Zawiera:
- panel meczów (na razie bez podłączonych danych),
- własne oceny i notatki zapisywane w lokalnej przeglądarce,
- generator kuponów AKO na podstawie prawdopodobieństw i kursów podanych przez użytkownika,
- eksport analiz i kuponów.

## Uruchomienie przez GitHub Pages
1. Otwórz repozytorium `pilkarska-analiza`.
2. Wejdź w **Settings**.
3. Z menu po lewej wybierz **Pages**.
4. W sekcji **Build and deployment** wybierz **Deploy from a branch**.
5. Jako branch wybierz `main`, folder `/ (root)`, a następnie kliknij **Save**.
6. Po chwili odśwież stronę Settings → Pages. GitHub pokaże adres opublikowanej strony.

## Ważne ograniczenia
Dane meczowe i kursy nie są jeszcze podłączone. Plik `data/matches.json` celowo nie zawiera fikcyjnych meczów ani prognoz. Model statystyczny, testy historyczne i automatyczne aktualizacje będą dodawane w kolejnych etapach. Generator AKO używa danych wejściowych użytkownika i nie gwarantuje zysku.

Nie umieszczaj tokenów API ani haseł w kodzie strony. Sekrety do automatyzacji powinny być przechowywane w GitHub Actions Secrets.
