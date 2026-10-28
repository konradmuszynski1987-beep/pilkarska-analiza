# Analiza piłkarska ⚽

Darmowa aplikacja webowa po polsku, przeznaczona do analizy statystycznej spotkań. Interfejs działa jako statyczna strona; część danych jest pobierana z publicznego, nieoficjalnego API ESPN.

## Funkcje

- Terminarz i wyniki dla 11 rozgrywek: Premier League, La Liga, Serie A, Bundesliga, Ligue 1, ligi portugalskiej, Eredivisie, ligi belgijskiej, Ligi Mistrzów, Ligi Europy i Ligi Konferencji.
- Model Poissona do obliczania prawdopodobieństw 1X2, BTTS i rynków bramkowych na podstawie ręcznie określonych wartości λ.
- Porównanie wpisanych kursów Fortuna/STS z prawdopodobieństwami modelu; kursy bukmacherów nie są pobierane automatycznie.
- Własne oceny meczów i notatki.
- Generator kuponów na podstawie zaimportowanych prawdopodobieństw i kursów.
- Dziennik typów z rozliczaniem, ROI i skutecznością; zwroty nie są liczone jako wygrane ani przegrane.
- Eksport i import lokalnej historii w JSON oraz eksport wyników backtestu do CSV.
- Test historyczny wyników z ostatnich 90 dni. Prognoza każdego meczu używa wyłącznie wcześniejszych spotkań; małe próbki drużyn są wygładzane średnią ligową. Wyniki są porównywane z prostą bazą ligową za pomocą Brier score i log loss.

## Uruchomienie przez GitHub Pages

1. Otwórz repozytorium `pilkarska-analiza`.
2. Wejdź w **Settings → Pages**.
3. W sekcji **Build and deployment** wybierz **Deploy from a branch**.
4. Ustaw branch `main` i folder `/ (root)), następnie zapisz.
5. Adres opublikowanej strony pojawi się w ustawieniach Pages. Jeśli publikacja jest już skonfigurowana, zmiany w repozytorium powinny zostać wdrożone zgodnie z konfiguracją projektu.

## Ważne ograniczenia

- ESPN jest źródłem nieoficjalnym. Dostępność i kompletność danych zależą od API oraz rozgrywek; nie gwarantujemy, że wszystkie ligi będą dostępne w każdej chwili.
- Kursy Fortuna i STS wpisuje użytkownik. Kurs fair modelu nie jest kursem oferowanym przez bukmachera.
- Model nie uwzględnia automatycznie składów, kontuzji, zawieszeń, pogody ani ruchów kursów.
- Backtest mierzy jakość prognoz na dostępnych wynikach, a nie rentowność zakładów. Lepszy wynik niż prosta baza ligowa nie gwarantuje przyszłej skuteczności.
- Dane ocen, obliczeń i dziennika typów są przechowywane w lokalnej przeglądarce. Mogą zniknąć po wyczyszczeniu jej danych; eksportuj kopię JSON. Import zastępuje lokalne dane po potwierdzeniu.
- Kupony AKO zakładają niezależność zdarzeń, więc ich wyliczona szansa może być niedokładna, szczególnie przy wspólnych meczach lub rynkach zależnych.

## Bezpieczeństwo

Nie umieszczaj tokenów API ani haseł w kodzie strony. Sekrety do automatyzacji powinny być przechowywane w GitHub Actions Secrets.
