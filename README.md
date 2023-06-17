# Dokumentacja Testów - Prosty stystem walki

> Projektu z zajęć "Wzorce Projektowe", Mateusz Jankowski 13832


## Spis Treści
* [Struktura aplikacji]
* [Scenariusze testów]
* [Wykorzystane narzędzia i biblioteki]
* [Ewentualne problemy i ich rozwiązania]


## A. Struktura aplikacji
Aplikaca słada się z następujących elementów:
- Klasa Bohater - reprezentuje bohatera w grze. Posiada atrybuty: name (nazwa bohatera), zdrowie (aktualne zdrowie bohatera) i moc (siła ataku bohatera). Zawiera metody Atak() (dokonuje ataku na przeciwnika) oraz is_alive() (sprawdza, czy bohater jest żywy).
- Funkcje wybierz_bohatera() i wybierz_przeciwnika() - służą do wyboru bohatera i przeciwnika przez gracza. Wyświetlają dostępne opcje i zwracają odpowiednie instancje klasy Bohater. W przypadku podania złej cyfry, wybrany zostaje specjalny bohater, który nie znajduję się na liście opcji.
- Funkcja walka(gracz, przeciwnik) - symuluje pojedynek między graczem a przeciwnikiem. Wyświetla informacje o rozpoczęciu walki oraz wykonuje kolejne ataki, aż jeden z bohaterów zostanie pokonany. Na koniec wyświetla informację o zwycięzcy i zwraca jego nazwę.
- Klasy testowe TestBohater i TestWalka - zawierają testy jednostkowe odpowiednio dla klasy Bohater i funkcji walka(). Testy te sprawdzają poprawność działania poszczególnych elementów aplikacji.
- Testy integracyjne - występują w sekcji kodu po wykonaniu testów jednostkowych. Wykonuje się je 10 razy dla klasy TestWalka w celu przetestowania interakcji między różnymi częściami aplikacji. Testy integracyjne sprawdzają, czy połączenie poszczególnych elementów, takich jak wybór bohatera i przeciwnika oraz rozpoczęcie walki, działa poprawnie i zgodnie z oczekiwaniami.
- Klasa TestWalkaAkceptacja - dziedzicząca po unittest.TestCase, zawiera test akceptacyjny test_walka_akceptacja. Testuje poprawność działania funkcji walka() dla konkretnych przypadków bohatera i przeciwnika.

## B. Scenariusze testów
- Test test_is_alive w klasie TestBohater sprawdza, czy metoda is_alive() zwraca poprawne wartości dla bohatera w zależności od jego aktualnego zdrowia.
- Test test_walka w klasie TestWalka sprawdza, czy funkcja walka() działa poprawnie i kończy się, gdy jeden z bohaterów zostanie pokonany.
- Test test_walka_akceptacja sprawdza, czy funkcja walka() zwraca oczekiwany wynik walki między konkretnymi bohaterami.

## C. Wykorzystane narzędzia i biblioteki
W aplikacji wykorzystano następujące narzędzia i biblioteki:
- Python - język programowania użyty do implementacji
- Moduł random - używany do generowania losowych wartości obrażeń podczas ataku.
- Moduł unittest - używany do tworzenia testów jednostkowych, integracyjnych i akceptacyjnych

## D. Ewentualne problemy i ich rozwiązania

Aktualnie brak w programie jakich kolwiek błędów. Jest to prosty kod wykonujący się w 100% poprawnie. Jedyne problemy mogą ewentualnie występować jeśli chodzi o różne kompilatory. W niektórych wersjach program może po prostu nie działać.
