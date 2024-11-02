# Data view example

## Introduction

W niniejszym artykule omówiony został przykład modelowania interfejsu użytkownika typowego zestawienia danych. Zestawienie to składa się z panelu filtrów i tabelarycznego zestawienia danych.

## Model

![Table component view](../../../img/data-table-view-model.png)

Na powyższym schemacie przedstawiony został model komponentu interfejsu użytkownika obsługującego wyświetlanie zestawienia danych w postaci tabelarycznej.

Zasady przechowywania i obsługi danych wewnątrz komponentu zostały opisane w wymaganiu `UI data processing rules`. Wymaganie to opisuje zasady organizacji danych, zasady ich przetworzenia, itp.

Komponent składa się z dwóch elementów:

* zestawu pól wprowadzania danych definiującego kryteria wyszukiwania danych
* tabeli zestawiającej wyszukiwane dane

Oba wymienione wyżej elementy mają uszczegółowienia przedstawione w postaci paneli powiązanych relacją `UI Details`.

Dane wyszukiwania to prosty formularz obejmujący:

* pole do wprowadzania danych tekstowych
* przycisk obsługujący odświeżanie danych zestawienia przy wykorzystaniu wprowadzonego kryterium wyszukiwania

Przykład nie pokazuje relacji między akcją wykonywaną w związku z obsługą zdarzenia naciśnięcia przycisku `Search`, a wywoływaną operacją API. Nie mniej jest to przewidywane przy wykorzystaniu relacji `UI Call`. Zasady obsługi akcji wykonywanej po naciśnięciu przycisku na diagramie przedstawione zostały w postaci wymagania `Search principles`.

Zestawienie danych przedstawione zostało w postaci dwóch wierszy. Pierwszy wiersz definiuje nagłówek widoczny dla użytkownika i zestawiający nazwy pokazywanych danych. Drugi wiersz jest informacją dla wykonawców pokazującą dane odczytanego zestawienia które mają być pokazane użytkownikowi. Opis szczegółów dla wykonania został zawarty powiązanym z panelem wymaganiem `Table display rules`.

W pierwszej kolumnie zestawienia wyświetlany jest element kontrolny umożliwiający z listą opcji umożliwiających wykonanie dodatkowych czynności przez użytkownika. Element ten ma uszczegółowienie pokazujące że obsługa tego ma być zrobiona w postaci kontrolki zawierającej jedną aktywną opcję `View` i możliwość rozwinięcia pozostałych opcji przez użytkownika po naciśnięciu przycisku. Rozwinięcie wyświetlane jest w postaci panelu zawierającego w układzie pionowym przyciski. Zasady wyświetlania i obsługi zawarta została w wymaganiu `Options display rules`.

Wybranie opcji `Modify` skutkuje uruchomieniem komponentu `modify-form` i wyświetleniem go w postaci panelu na przypiętego do prawej strony widoku użytkownika. Komponent modyfikacji ma swój projekt na diagramie `UI Design: Modify-form`.
