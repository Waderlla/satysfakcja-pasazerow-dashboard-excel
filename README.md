# Analiza satysfakcji pasażerów – Dashboard w Excelu

## Opis projektu
Projekt przedstawia analizę satysfakcji pasażerów linii lotniczych na podstawie ankiety obejmującej **19 652 odpowiedzi**. Dane zawierają oceny różnych elementów podróży oraz informacje demograficzne i operacyjne (m.in. opóźnienia).
Celem było zrozumienie, które elementy podróży mają największy wpływ na ogólną ocenę lotu oraz jak satysfakcja różni się w zależności od klasy podróży, typu klienta, demografii i opóźnień.

Efektem końcowym jest **interaktywny dashboard w Excelu** składający się z dwóch stron, z możliwością filtrowania za pomocą **segmentatorów (slicerów)** oraz z przyciskiem resetowania filtrów (makro VBA).

---

## Struktura pliku
- **Oceny_unpivot** - tabela przekształcona do formatu „długiego”, umożliwiającego analizę czynników.
- **Ankieta** - dane źródłowe z badania satysfakcji pasażerów.
- **Analiza** - tabele przestawne i obliczenia pomocnicze (Top 3/Bottom 3, średnie wg segmentów, przygotowanie danych do wykresów).
- **Dashboard_strona_1** - wizualizacja: satysfakcja pasażerów i demografia.
- **Dashboard_strona_2** - wizualizacja: oceny poszczególnych elementów podróży, radar „segment vs średnia”.
- **Dashboard_wnioski_i_rekomen.** - tekstowe podsumowanie najważniejszych obserwacji i rekomendacji (arkusz narracyjny).

---

## Wykorzystane narzędzia i techniki
- **Excel** - główne narzędzie analizy i wizualizacji.
- **Tabele przestawne i wykresy przestawne** - agregacja danych i tworzenie interaktywnych wizualizacji.
- **Segmentatory (slicery)** - filtrowanie wyników wg płci, klasy podróży, typu podróży i typu klienta.
- **Makra VBA** - przycisk resetowania segmentatorów (oddzielnie dla każdej strony dashboardu). Makra są wykorzystywane wyłącznie do resetowania filtrów i nie modyfikują danych źródłowych.
- **Formatowanie warunkowe** - automatyczne wyróżnianie najlepszych i najgorszych czynników.
- **Formuły i logika obliczeń**:
  - `IF` - logika warunkowa (np. przypisanie wartości do Top 3/Bottom 3),
  - `LARGE` i `SMALL` - wyszukiwanie najwyższych i najniższych wartości,
  - `VLOOKUP` / odwołania do tabel przestawnych - porównanie średnich ocen segmentów z ogólną średnią,
  - odwołania do tabel przestawnych - zasilanie tabel pomocniczych.
- **Tabele pomocnicze** - do sterowania kolorem słupków (Top 3/Bottom 3), do przygotowania porównania segmentu z oceną ogólną (radar), do prawidłowego wyświetlania wykresów typu donut.
- **Wykresy**:
  - KPI w kafelkach (liczba lotów, średnia ocena, średnie opóźnienie, punktualność),
  - wykresy kolumnowe (demografia, klasy podróży),
  - donut (udział zadowolonych vs niezadowolonych),
  - linia (satysfakcja i oceny vs opóźnienia),
  - wykres radarowy (profil segmentu vs średnia ogólna).
- **UX w dashboardzie** - przemyślany układ (dwie strony tematyczne), spójna kolorystyka (ciemne tło + wyróżnienia), stała lokalizacja segmentatorów, kafelki KPI u góry, przycisk „wyczyść filtry” dla wygody użytkownika.

---

## Kluczowe wnioski
- **Ogólny poziom satysfakcji jest niski** - tylko **43,7% pasażerów jest zadowolonych**, a średnia ocena to **3,2/5**.
- **Najlepiej oceniane elementy**: obsługa w trakcie lotu, obsługa bagażu, komfort siedzeń.
- **Najgorzej oceniane elementy**: WiFi, proces rezerwacji, punktualność (opóźnienia).
- **Klasa podróży** ma duży wpływ:
  - Biznes → ~70% zadowolonych,
  - Economy → tylko 19%.
- **Typ podróży**: służbowe oceniane znacznie lepiej (59% zadowolonych) niż prywatne (10%).
- **Opóźnienia** obniżają satysfakcję - przy opóźnieniu <15 minut zadowolonych jest 46%, a przy opóźnieniu >1h już tylko 32%.

---

## Rekomendacje
- Priorytetem powinna być **poprawa jakości WiFi i procesu rezerwacji**, bo to najniżej oceniane elementy.
- **Komfort klasy Economy** (siedzenia, przestrzeń na nogi) warto poprawić, aby zmniejszyć różnicę względem klasy Biznes.
- **Boarding online** jest czynnikiem, który najmocniej różnicuje zadowolonych od niezadowolonych - jego poprawa może szybko zwiększyć satysfakcję.
- **Punktualność** to fundament - ograniczenie opóźnień nawet o kilkanaście minut podniosłoby wyniki satysfakcji.

---

## Pliki w repozytorium
- `Ankieta.csv` - dane źródłowe.
- `satysfakcja-pasazerow-analiza-lotow.xlsm` - gotowy dashboard z makrami (VBA) (2 strony, slicery).
- `satysfakcja-pasazerow-analiza-lotow.xlsx` - wersja bez makr (podgląd; 2 strony, slicery).
- `README.md` - opis projektu (ten plik).