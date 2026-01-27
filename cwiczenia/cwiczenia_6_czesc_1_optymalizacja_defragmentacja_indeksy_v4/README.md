Ćwiczenia 6 część 1 -- optymalizacja, defragmentacja, indeksy
1.  Uruchomić Apache i MySql.
2.  Zaimportuj bazę sklep z moodla.
3.  Z pomocą phpMyAdmin (sprawdzaj podgląd SQL):
![](media/image1.png)
a)  utwórz indeks prosty dla tabeli towary, kolumna producent (rodzaj
    BTREE )
b)  utwórz indeks unikatowy dla tabeli towary, kolumna cena (rodzaj HASH
    )
c)  utwórz indeks dla tabeli towary, kolumna data sprzedaży
d)  utwórz indeks pełny tekst dla tabeli towary, kolumna nazwa( dodaj
    komentarz )
e)  utwórz indeks złożony dla tabeli towary, kolumny cena i waga
f)  utwórz indeks złożony i unikatowy dla tabeli towary, kolumny
    producent i nazwa
g)  utwórz indeks przestrzenny dla tabeli punkty, kolumna kształt typ
    geometry (wstawić dane do jednego rekordu wsk. ST_GeomFromText... )
h)  ![](media/image2.png)
> ![](media/image3.png)
i)  przejrzyj utworzone indeksy i wykonaj kopię bazy
j)  usuń wszystkie utworzone indeksy
