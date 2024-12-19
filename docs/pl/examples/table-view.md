# Przykład interfejsu użytkownika zestawienia tabelarycznego z panelem filtrów

## Wprowadzenie

W niniejszym artykule omówiony został przykład modelowania interfejsu użytkownika typowego zestawienia danych. Zestawienie to składa się z panelu filtrów i tabelarycznego zestawienia danych.

## Model

![Table component view](../../img/data-table-view-model.png)

Na powyższym schemacie przedstawiony został model komponentu interfejsu użytkownika obsługującego wyświetlanie zestawienia danych w postaci tabelarycznej.

Zasady przechowywania i obsługi danych wewnątrz komponentu zostały opisane w wymaganiu `UI data processing rules`.

Komponent składa się z dwóch elementów:

* zestawu pól umożliwiających wprowadzenie kryteriów wyszukiwania,
* tabeli zestawiającej wyszukane dane.

Oba wymienione wyżej elementy mają uszczegółowienia przedstawione w postaci paneli powiązanych relacją `UI Details`.

Dane kryteriów wyszukiwania to prosty formularz obejmujący:

* pole do wprowadzania danych tekstowych,
* przycisk obsługujący odczyt i odświeżenie zestawienia tabelarycznego danych.

Naciśnięcie przycisku `Search` skutkuje wywołaniem operacji `getSomething`, która czyta dane. Po odczycie następuje odświeżenie zestawienia tabelarycznego. Zasady obsługi wywołania operacji opisane zostały w `Search rules`. Operacja `getSomething` jest powiązany z przyciskiem relacją `UI Call`.

Na diagramie tabelaryczne zestawienie danych przedstawione zostało w postaci dwóch wierszy (wykorzystane do tego zostały panele). Pierwszy wiersz to nagłówek. Kolejny wiersz reprezentuje dane pokazywane w tabeli. Nagłówek prezentuje etykiety pól danych wyświetlanych w wierszach danych. W wierszu danych pokazane zostały nazwy pól pozycji listy zwróconej przez operację `getSomething`. Szczegółowy opis zasad mapowania danych został zawarty w, powiązanym z panelem, wymaganiu `Table display rules`.

W każdym wierszu w pierwszej kolumnie pozycji zestawienia wyświetlane jest menu kontekstowe. Na diagramie element ten ma uszczegółowienie w postaci panelu zawierającego element listy nawigacyjnej menu. Użytkownik widzi domyślnie opcję `View`. Po kliknięciu w przycisk rozwinięcia wyświetlana jest lista dostępnych opcji. Panel jest pozycjonowany pod menu (na diagramie przedstawione to jest w postaci relacji `UI Show` z atrybutem `Position` równym `Below`). Zasady wyświetlania i obsługi opcji menu zawarte zostały w wymaganiu `Options display rules`.

Wybranie opcji `Modify` skutkuje uruchomieniem komponentu `modify-form`. Komponent modyfikacji ma swój projekt na diagramie `UI Design: Modify-form`.
