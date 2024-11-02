# Form example

## Wprowadzenie

W niniejszym artykule omówiony został przykład modelu prostego formularza służącego do edycji danych.

## Model

![Modify form](../../../img/modify-form-model.png)

Na powyższym schemacie przedstawiony został model interfejsu użytkownika prostego formularza modyfikacji danych.

Formularz jest uruchamiany z ustawieniem atrybutów opisanych w wymaganiu `Component attributes processing rules`. Przyjęto że atrybuty stanowią dane wejściowe przekazywane do komponentu w momencie uruchamiania.

Dane formularza obsługiwane zgodnie z zasadami opisanymi w `UI data processing rules`.

Formularz składa się z następujących elementów:

* panel danych edycji
* panel operacji

Oba mają uszczegółowienie powiązane relacją `UI Details`.
