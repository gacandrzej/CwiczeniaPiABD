Ćwiczenia 3 -- nadawanie uprawnień, role
1.  Utwórz kopię katalogu c:\\xampp\\mysql do folderu dokumenty.
2.  Uruchomić Apache i MySql.
3.  Otworzyć dokumentację dla MariaDB 10..., np.:
<https://mariadb.com/kb/en/authentication-plugin-mysql_native_password/>
<https://mariadb.com/kb/en/create-role/>
<https://mariadb.com/kb/en/grant/>
<https://mariadb.com/kb/en/revoke/>
<https://mariadb.com/kb/en/show-privileges/>
4.  Od tego punktu pracujemy w Shellu!!! Dodać trzech użytkowników
    monika blazejXYZ i iwonaXYZ.
5.  Utwórz odpowiednie bazy dla użytkowników, czyli monika, Henryk i
    Ryszard.
6.  Utworzyć bazę o nazwie wspolnaXYZ z dwiema tabelami test i test2. Do
    test dodać 2 rekordy danych.
7.  Nadać obu kontom uprawnienia do nowo założonej bazy.
8.  Sprawdzić logowanie ( **mysql --u konto --p** ) dla kont: monika,
    blazejXYZ i iwonaXYZ.
9.  Podłączyć się do baz: monika, blazejXYZ, iwonaXYZ i wspolnaXYZ.( use
    baza)
10. Wylogować się z wszystkich kont.
11. Przeloguj się na konto root .
![](media/image1.png)
![](media/image2.png)
12. Sprawdź istniejące konta na serwerze:
![](media/image3.png)
13. Sprawdź listę dostępnych uprawnień: ( SHOW privileges; )
![](media/image4.png)
14. Nadać uprawnienia dla wszystkich kont ( GRANT lista_uprawnień on
    baza.tabela to user@host wszystkie, lub tylko wybrane)
![](media/image5.png)
15. Sprawdź czy nadałeś/aś uprawnienia poprawnie.
![](media/image6.png)
16. Odśwież uprawnienia:
![](media/image7.png)
17. Odebrać **wybrane** uprawnienia użytkownikom blazejXYZ, iwonaXYZ i
    monika (REVOKE ...
np.: REVOKE grant option, select ON baza.\* FROM user@localhost; )
![](media/image8.png)
18. Wykonać instrukcje **kilka razy** GRANT, REVOKE zmieniając za każdym
    razem parametry, sprawdzać uprawnienia za każdym razem.
( np. SHOW GRANTS FOR BlazejXYZ@localhost; )
![](media/image9.png)
Część 3 -- Tworzenie ról
19. ![](media/image10.png)
    Utwórz rolę webmasterzy i adminiSQL.
20. Nadaj uprawnienie SELECT dla webmasterów, a insert, update, delete
    dla adminiSQL.
![](media/image11.png)
21. Z poziomu konta monika przypisz się do roli webmaster:
![](media/image12.png)
Wymagana modyfikacja WITH ADMIN:
![](media/image13.png)
22. Sprawdź uprawnienia dla moniki:
![](media/image14.png)
23. Sprawdź nadane uprawnienia dla ról:
> ![](media/image15.png)
24. Przypisz użytkowników blazejXYZ i iwonaXYZ do tych ról.
![](media/image16.png)
![](media/image17.png)
25. Sprawdź uprawnienia dla kont odpowiednimi komendami:
Dla Błażeja:
![](media/image18.png)
Dla Iwony:
![](media/image19.png)
26. Ustaw domyślną rolę dla Moniki na programiści;
![](media/image20.png)
![](media/image21.png)
Sprawdzenie:
![](media/image22.png)
27. Zmodyfikuj obie role i sprawdź uprawnienia odpowiednimi komendami.
![](media/image23.png)
GRANT:
> ![](media/image24.png)
28. Dodaj rolę programiści do roli adminiSQL;
> ![](media/image25.png)
29. Sprawdź uprawnienia dla adminiSQL:
![](media/image26.png)
30. Zdejmij role użytkownikom.
![](media/image27.png)
![](media/image28.png)
31. Wyświetl wszystkie role i konta:
![](media/image29.png)
32. Ustaw bieżącą rolę dla Iwony na programiści, a następnie na none:
![](media/image30.png)
33. Usuń role. ( DROP ROLE ...)
> ![](media/image31.png)
34. ![](media/image32.png)
    Usunąć konta monika, blazejXYZ i
    iwonaXYZ oraz marek o ile istnieją.( DROP USER ...
35. Usunąć założone bazy. ( DROP DATABASE ... )
> ![](media/image33.png)
36. Utwórz kopię katalogu mysql.
37. Zatrzymać usługi Apache i MySql.
38. KONIEC
