# Opis zbioru danych

Dane pochodzą z dwóch źródeł:

- popyt na pracę  (popyt; próba losowa, 10 984 obserwacji, dane poddane obróbce i są pozmieniane w porównaniu do danych rzeczywistych)
- centralna baza ofert pracy  (cbop; próba nielosowa, 9 469 obserwacji)
- częśc wspólna dwóch baz: 505

Zbiór zawiera 20 958 obserwacji oraz 14 zmiennych, które nazywają się następująco:

+ id_popyt -- identyfikator rekordu z badania popyt na pracę
+ id_jednostki -- identyfikator jednostki (firmy)
+ waga -- waga finalna
+ sek -- sektor (1 = publiczny, 2 = prywatny)
+ klasa_pr -- wielkość (M = małe, S = średnie, D = Duże)
+ sekc_pkd -- sekcja PKD (pogrupowana)
+ woj -- województwo
+ zawod_kod2 -- zawod (1 cyfra, zgodnie z http://www.klasyfikacje.gofin.pl/kzis/6,0.html)
+ wolne_miejsca -- liczba deklarowanych wolnych miejsc
+ id_cbop -- identyfikator z CBOP
+ jedna_zmiana -- czy wakaty były na jedną zmianę (TRUE = tak, FALSE  = nie)
+ wymiar_40 -- czy wymiar pracy wynosił 40 godzin (TRUE = tak, FALSE  = nie)
+ wolne_miejsca_cbop -- liczba deklarowanych wolnych miejsc pracy
+ wolne_miejsca_niepeln_cbop -- liczba deklarowanych wolnych miejsc pracy dla niepełnosprawnych

Dane możemy wczytac wykorzystując podstawowe funkcje R

```r
dane <- read.csv("popyt-zajecia-dane.csv", stringsAsFactors = F)

```

Pierwsze 6 wierszy 

```r
> head(zajecia)
  id_popyt                             id_jednostki waga sek klasa_pr sekc_pkd woj zawod_kod2 wolne_miejsca id_cbop jedna_zmiana wymiar_40 wolne_miejsca_cbop wolne_miejsca_niepeln_cbop
1        1 a9cc990df6a99ab215a1bc13f51d4825c7d52d18    1   1        D        O  14          1             2      NA           NA        NA                 NA                         NA
2        2 a9cc990df6a99ab215a1bc13f51d4825c7d52d18    1   1        D        O  14          2             7      NA           NA        NA                 NA                         NA
3        3 c9dbaf50890165ebe810aa770de0e9df903dc35b    6   1        D        O  24          2             6      NA           NA        NA                 NA                         NA
4        4 718e0bba42bcec6ed98f9690db6d26cb7b93c880    1   1        D      R.S  14          2             7      NA           NA        NA                 NA                         NA
5        5 532a1879a692b9d7bbb7282ba757d028156ef341    1   1        D      R.S  14          2             6      NA           NA        NA                 NA                         NA
6        6 0b6b623fa45e257284a3049d097af322841337e3    1   1        D      R.S  22          2             1      NA           NA        NA                 NA                         NA
```

Uwaga: braki danych w kolumnie `id_popyt` oznaczają, że dane pochodzą z CBOP, a braki w `id_cbop` oznaczają dane z popytu.