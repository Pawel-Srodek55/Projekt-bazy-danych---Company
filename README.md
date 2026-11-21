# Company — relacyjna baza danych w SQL Server

Projekt zaliczeniowy polega na zaimportowaniu sześciu dokumentów JSON o firmach do relacyjnej bazy danych. Docelowe tabele mają spełniać 1NF, 2NF i 3NF. Zagnieżdżone dane, takie jak biura i produkty, trafiają do powiązanych tabel. W docelowej bazie dane są przechowywane w postaci relacyjnej.

## Kolejność uruchamiania

Uruchamiaj skrypty w SSMS na pustej bazie testowej. Przed wykonaniem każdego pliku sprawdź, czy masz wybraną właściwą bazę. Po wykonaniu sprawdź zakładkę **Messages**. Jeśli pojawi się błąd, usuń jego przyczynę przed przejściem do następnego kroku.

| Krok | Plik | Co robi |
|---|---|---|
| 1 | `sql/01_schema.sql` | Tworzy tabele, klucze główne i obce oraz ograniczenia `UNIQUE`, `CHECK` i `DEFAULT`. Dodaje opisy tabel w bazie. |
| 2 | `sql/02_import.sql` | Wczytuje sześć dokumentów z `data/companies documents 1-6.json` i zapisuje dane w odpowiednich tabelach. |
| 3 | `sql/03_objects.sql` | Tworzy widok, procedurę składowaną i funkcję użytkownika. |
| 4 | `sql/04_roles.sql` | Tworzy role i użytkowników lokalnych w bazie oraz nadaje uprawnienia. |
| 5 | `sql/05_verify.sql` | Sprawdza wyniki importu. Działanie uprawnień sprawdzamy także po zalogowaniu na konta testowe. |

## Praca zespołowa

Każdy pracuje na własnej bazie testowej. Zmiany w skryptach zapisujemy na osobnych gałęziach i zgłaszamy przez pull request do `main`. Przed scaleniem jedna z pozostałych osób sprawdza i zatwierdza zmiany. Po pobraniu aktualnego `main` uruchamiamy odpowiednie skrypty w SSMS. Git aktualizuje pliki projektu, a wykonanie skryptów aktualizuje bazę.
