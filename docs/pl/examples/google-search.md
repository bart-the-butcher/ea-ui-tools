# Modelowanie interfejsu użytkownika na przykładzie wyszukiwarki Google

## Wprowadzenie

W niniejszym artykule omówiony został przykład wykorzystania modelowania interfejsów użytkownika w oparciu o wyszukiwarkę udostępnianą przez Google.

Przedstawiony model nie pokazuje pełnej złożoności wyszukiwarki Google. Pewne jej elementy zostały celowo pominięte, żeby zmniejszyć złożoność modelu.

## Wyszukiwarka Google

Na poniższym rysunku pokazana została strona wyszukiwarki:

![Wyszukiwarka Googla](../../img/google-search.png)

Interfejs użytkownika wyszukiwarki można podzielić na 3 obszary:

* panel nagłówka (1)
* panel wyszukiwarki (2)
* panel stopki (3)

Podział przedstawiono na poniższym rysunku:

![Obszary wyszukiwarki Google](../../img/google-search-areas.png)

Panele nagłówka i wyszukiwarki to obszary funkcjonalne. Oprócz interfejsu użytkownika umożliwiającego wyszukiwanie, mamy możliwości zmiany trybu pracy, mamy opcje przejścia do innych usług udostępnianych przez Google.

Panel stopki to obszar informacyjny zawierający wymagane prawem informacje regulaminów i zasad poufności.

## Model

Poniższy obrazek pokazuje wyszukiwarke Google w postaci modelu przy użyciu opisywanych narzędzi:

![Model wyszukiwarki Google](../../img/google-search-model.png).

Wyszukiwarka została przedstawiona w postaci komponentu składającego się z 3 paneli. Każdy z paneli posiada uszczegółowienie. Panele obsługujące obszary 1 i 3 obsługują głównie linki albo do innych usług Google albo do informacji (regulamin, itp). Link w modelu przedstawiony jest w postaci przycisku. Kliknięcie w niego powoduje przejście do funkcjonalności opisanej w postaci komponentu. Do opisu przejścia wykorzystano relację `UI Navigate`. Na uwagę zasługuje opcja znajdująca się po lewej stronie przycisku `Sign in`. Opcja ta została przedstawiona przy pomocy przycisku, do którego dowiązany jest panel przy pomocy relacji `UI Show` z atrybutem `Position` ustawionym na `Below`. W ten sposób kliknięcie w przycisk skutkuje wyświetleniem powiązanego panelu w miejscu pod przyciskiem. Panel zestawia usługi Google. Usługi te zostały pokazane w postaci listy. W każdym wierszu listy wyświetlane są 3 panele. Każdy z nich reprezentuję dostępną dla użytkownika usługę Google. Kliknięcie w niego skutkuje uruchomienie wskazanej usługi. Na modelu wykorzystano uszczegółowienie `UI Details`. Powiązanie z usługą nie zostało pokazane.

Obszar 2 opisuje podstawową funkcjonalność wyszukiwarki. Oprócz obrazka loga Google zawiera element umożliwiający wprowadzenie poszukiwanej frazy. Oprócz tego pokazywane są dodatkowe opcje. Wprowadzenie frazy w pole edycyjne lub naciśnięcie przycisku znajdującego się po lewej stronie pola edycyjnego skutkuje wyświetleniem panelu z podpowiedziami.

Panel ten jest wyświetlany pod polem edycyjnym (na modelu przedstawione zostało to przez połączenie przycisku z panelem przy pomocy relacji `UI Show` z atrybutem `Position` równym `Below`. Został wymodelowany w postaci listy elementów i przycisków opcji. Pozycja ma uszczegółowienie w postaci panelu zawierającego ikonę, podpowiedź i temat. Zasady wyświetlania danych podpowiedzi opisane zostały w dowiązanym do panelu wymaganiu.

Na szczególną uwagę zasługuje przycisk otwierający klawiaturę ekranową. Przycisk ten został zlokalizowany po prawej stronie elementu edycyjnego wyszukiwarki. Relacja (`UI Show As`) wiążącą ten przycisk z komponentem obsługującym klawiaturę ekranową opisuje sposób wyświetlenia jako nakładkę nieblokującą dostępu do przykrywanych opcji, wyświetlaną w prawym dolnym rogu widoku przeglądarki. Jest to opisane na relacji przy wykorzystaniu atrybutu `Type` o wartości `Overlay` i `Position` o wartości `Bottom Right`.