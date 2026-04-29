# Ćwiczenia 10 -- replikacja bazy

💡Uwaga: praca w parach na dwóch komputerach

1. Uruchomić Apache i MySql.

1. Zaimportuj 3,4 bazy danych z kopii zapasowej.

1. Jeśli replikacja działa, zakomentuj wpisy w pliku my.ini i
    zrestartuj MySql.

1. Z pomocą phpMyAdmin utwórz replikację serwera głównego (master).
    Zakładka replikacja dla 3 baz.

   ![image1](media/image1.png)

1. Zapisz ustawienia w pliku my.ini w sekcji [mysqld]:

   ```ini
    server-id=766
    log_bin=mysql-bin
    log_error=mysql-bin.err
    binlog_do_db=sklep
    binlog_do_db=korpo
    binlog_do_db=osoby
   ```

1. Stwórz konto o nazwie replik z uprawnieniem REPLICATION SLAVE.

1. Sprawdź w Shellu status serwera głównego: SHOW MASTER STATUS;

   ![image2](media/image2.png)

1. Wykonaj zapytanie:

   ```sql
   SELECT * FROM baza.tabela; 
   ```

   dla wybranej bazy i tabeli.

1. Wykonaj polecenie

   ```sql
   SHOW processlist;
   ```

1. Wykonaj polecenie SHOW SLAVE HOSTS;
1. Sprawdź w phpMyAdmin w zakładce STATUS procesy i stan serwera.
1. Wykonaj kopię zapasową 3 baz z opcją --master-data do pliku
    kopia.sql. Skopiuj plik na drugi komputer.
1. Na drugim komputerze skonfiguruj serwer podrzędny (slave).
1. Odtwórz dane z pliku kopia.sql.
1. Otwórz plik my.ini
server-id=2
report-host='twoja_nazwa_serwera'
1. Uruchom Shella i sprawdź połączenie z serwerem głównym:
ping ip
mysql --u replik -p
1. Jeśli można się zalogować, to przełącz się na konto Root.
1. Wydaj komendę:
CHANGE MASTER TO MASTER_HOST=\<host\>, MASTER_PORT=\<port\>,
MASTER_USER=\<user\>, MASTER_PASSWORD=\<password\> ,
MASTER_LOG_FILE = \'master_log_name\', MASTER_LOG_POS = master_log_pos;
1. Jeśli polecenie wykona się poprawnie to START SLAVE.
1. Jeśli polecenie wykona się poprawnie to SHOW SLAVE STATUS.
1. Sprawdź w phpMyAdmin w zakładce STATUS procesy i stan serwera.
1. Na serwerze głównym wykonaj polecenie SHOW SLAVE HOSTS;
1. Dodaj record na serwerze głównym i sprawdź czy pojawił się na
    serwerze slave.
1. Wykonaj na serwerze podrzędnym zapytanie SELECT \* FROM baza.tabela;
    (dla wybranej bazy i tabeli)
1. Sprawdź zawartość pliku master.info na serwerze slave.
1. Zmodyfikuj użytkownika replik i serwer master tak, aby można było
    replikować bazy za pomocą połączeń szyfrowanych SSL.
