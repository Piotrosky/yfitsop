# Dokumentacja projektu zaliczeniowego

*Przedmiot*: Inżynieria oprogramowania  
*Temat*: Aplikacja do streamingu muzyki  
*Autorzy*: Piotr Piotrowski i Dorian Sobierański  
*Grupa*: 214A  
*Kierunek*: Informatyka  
*Rok akademicki*: II  
*Poziom i semestr*: I/4  
*Tryb studiów*: Stacjonarne

---

## Spis Treści

1. [Odnośniki do innych źródeł](#odnośniki-do-innych-źródeł)
2. [Słownik pojęć](#słownik-pojęć)
3. [Wprowadzenie](#4-wprowadzenie)
    1. [Cel dokumentacji](#cel-dokumentacji)
    2. [Przeznaczenie dokumentacji](#przeznaczenie-dokumentacji)
    3. [Opis organizacji lub analiza rynku](#opis-organizacji-lub-analiza-rynku)
    4. [Analiza SWOT organizacji](#analiza-swot-organizacji)
4. [Specyfikacja wymagań](#specyfikacja-wymagań)
    1. [Charakterystyka ogólna](#charakterystyka-ogólna)
    2. [Wymagania funkcjonalne](#wymagania-funkcjonalne)
    3. [Wymagania niefunkcjonalne](#wymagania-niefunkcjonalne)
5. [Zarządzanie projektem](#zarządzanie-projektem)
    1. [Zasoby ludzkie](#zasoby-ludzkie)
    2. [Harmonogram prac](#harmonogram-prac)
    3. [Etapy/kamienie milowe projektu](#etapykamienie-milowe-projektu)
6. [Zarządzanie ryzykiem](#zarządzanie-ryzykiem)
    1. [Lista czynników ryzyka](#lista-czynników-ryzyka)
    2. [Ocena ryzyka](#L162)
    3. [Plan reakcji na ryzyko](#plan-reakcji-na-ryzyko)
7. [Zarządzanie jakością](#zarządzanie-jakością)
    1. [Scenariusze i przypadki testowe](#scenariusze-i-przypadki-testowe)
8. [Projekt techniczny](#projekt-techniczny)
    1. [Opis architektury systemu](#opis-architektury-systemu)
    2. [Technologie implementacji systemu](#technologie-implementacji-systemu)
    3. [Diagramy UML](#diagramy-uml)
    4. [Charakterystyka zastosowanych wzorców projektowych](#charakterystyka-zastosowanych-wzorców-projektowych)
    5. [Projekt bazy danych](#projekt-bazy-danych)
    6. [Projekt interfejsu użytkownika](#projekt-interfejsu-użytkownika)
    7. [Procedura wdrożenia](#procedura-wdrożenia)
9. [Dokumentacja dla użytkownika](#dokumentacja-dla-użytkownika)
10. [Podsumowanie](#podsumowanie)
11. [Szczegółowe nakłady projektowe członków zespołu](#szczegółowe-nakłady-projektowe-członków-zespołu)
12. [Inne informacje](#inne-informacje)

---

## 2 Odnośniki do innych źródeł

- *Zarządzanie projektem*: Jira, Trello, itp.
- *Wersjonowanie kodu*: Git (hosting np. na Bitbucket lub Github), ew. SVN
- *System obsługi defektów*: np. Bitbucket, Github, Bugzilla.

---

## 3 Słownik pojęć

Tabela lub lista z pojęciami, które wymagają wyjaśnienia, wraz z tymi wyjaśnieniami – w szczególności synonimy różnych pojęć używanych w dokumentacji.

---

## 4 Wprowadzenie

### 4.1 Cel dokumentacji

Celem dokumentacji jest przedstawienie szczegółowych informacji dotyczących systemu Yfitsop, w tym jego specyfikacji, wymagań funkcjonalnych i niefunkcjonalnych, technologii implementacji oraz zarządzania projektem.

### 4.2 Przeznaczenie dokumentacji

Dokumentacja jest przeznaczona dla zespołu projektowego, przyszłych deweloperów oraz użytkowników systemu.

### 4.3 Opis organizacji lub analiza rynku

- *Jeśli dla konkretnej organizacji*: Opis organizacji, dla której realizowany będzie system, jej procesów biznesowych.
- *Jeśli na masowy rynek*: Pobieżna analiza rynku, docelowi użytkownicy, organizacje, ich rodzaje.

### 4.4 Analiza SWOT organizacji

| *Silne strony* | *Słabe strony* |
|------------------|------------------|
| Przykład 1       | Przykład 2       |
| *Szanse*       | *Zagrożenia*   |
| Przykład 3       | Przykład 4       |

---

## 5 Specyfikacja wymagań

### 5.1 Charakterystyka ogólna

#### 5.1.1 Definicja produktu

Yfitsop to aplikacja webowa typu Spotify-clone, umożliwiająca strumieniowe odtwarzanie muzyki. Projekt wykorzystuje technologie Python (Django) i TailwindCSS.

#### 5.1.2 Podstawowe założenia

- Przeglądanie dostępnej biblioteki muzycznej
- Wyszukiwanie utworów według nazwy
- Tworzenie i zarządzanie playlistami
- Odtwarzanie utworów w interfejsie webowym

#### 5.1.3 Cel biznesowy

Celem jest stworzenie platformy do streamingu muzyki jako baza do dalszego rozwoju oraz nauki technologii webowych.

#### 5.1.4 Użytkownicy

- *Zarejestrowani użytkownicy*: Mogą odtwarzać muzykę i zarządzać playlistami.
- *Administratorzy*: Mają dostęp do zarządzania treścią.

#### 5.1.5 Korzyści z systemu

- K-001: Użytkownicy mogą słuchać muzyki online.
- K-002: Użytkownicy mogą wyszukiwać utwory po nazwie.
- K-003: Użytkownicy mogą tworzyć i zarządzać playlistami.
- K-004: Administratorzy mogą dodawać nowe utwory do bazy danych.

#### 5.1.6 Ograniczenia projektowe i wdrożeniowe

- *Backend*: Python (Django)
- *Frontend*: TailwindCSS
- *Baza danych*: PostgreSQL
- *Przeglądarki*: Chrome, Firefox, Edge

Brak możliwości uploadu plików i rekomendacji. Dane użytkowników zgodne z polityką RODO.

### 5.2 Wymagania funkcjonalne

#### 5.2.1 Lista wymagań

- *Odtwarzanie muzyki*: Użytkownik może odtwarzać muzykę za pomocą odtwarzacza.
- *Tworzenie playlisty*: Użytkownik może tworzyć i zarządzać playlistami.
- *Wyszukiwanie utworów*: Użytkownik może wyszukiwać utwory po nazwie, artyście, albumie.
- *Zarządzanie kontem*: Rejestracja, logowanie, zmiana danych użytkownika.

#### 5.2.2 Diagramy przypadków użycia

![image](https://github.com/user-attachments/assets/7430ccb3-5fb9-4f6c-a045-7e1c9e604690)

#### 5.2.3 Szczegółowy opis wymagań

*Numer (ID)*: F-001  
*Nazwa*: Odtwarzanie muzyki  
*Uzasadnienie biznesowe*: K-001: Użytkownicy mogą słuchać muzyki online.  
*Użytkownicy*: Zarejestrowani użytkownicy.  
*Scenariusz*: Odtwarzanie wybranego utworu.

*Numer (ID)*: F-002  
*Nazwa*: Tworzenie playlisty  
*Uzasadnienie biznesowe*: K-003: Użytkownicy mogą tworzyć i zarządzać playlistami.  
*Użytkownicy*: Zarejestrowani użytkownicy.  
*Scenariusz*: Tworzenie nowej playlisty.

---

## 6 Zarządzanie projektem

### 6.1 Zasoby ludzkie

Założenie, że projekt byłby realizowany w całości jako projekt komercyjny.

### 6.2 Harmonogram prac

Wskazać czasy trwania poszczególnych etapów i zadań – wykres Gantta.

### 6.3 Etapy/kamienie milowe projektu

1. Faza wstępna: Określenie wymagań, wybór technologii
2. Faza projektowania: Stworzenie schematów UML, projektowanie interfejsu
3. Faza implementacji: Programowanie
4. Faza testowania: Testowanie aplikacji
5. Faza wdrożenia: Wdrożenie aplikacji na serwer

---

## 7 Zarządzanie ryzykiem

### 7.1 Lista czynników ryzyka

1. Niska jakość kodu, brak testów.
2. Ograniczona wiedza z zakresu wybranej technologii.
3. Możliwość opóźnienia w harmonogramie.

### 7.2 Ocena ryzyka

| *Czynnik* | *Prawdopodobieństwo* | *Skala wpływu* | *Ocena ryzyka* |
|-------------|-----------------------|------------------|------------------|
| Wysokie ryzyko | 3 | 3 | 9 |

### 7.3 Plan reakcji na ryzyko

Plan reakcji w przypadku wystąpienia opóźnień w harmonogramie – dodatkowe godziny pracy, pomoc z zewnątrz.

---

## 8 Zarządzanie jakością

### 8.1 Scenariusze i przypadki testowe

- *Testowanie funkcji wyszukiwania*: Sprawdzenie poprawności wyników wyszukiwania utworów.
- *Testowanie odtwarzania muzyki*: Sprawdzenie, czy utwór jest odtwarzany poprawnie.
  
---

## 9 Projekt techniczny

### 9.1 Opis architektury systemu

System Yfitsop oparty jest na architekturze trójwarstwowej:

Warstwa prezentacji (frontend) – odpowiedzialna za interakcję z użytkownikiem, zbudowana z użyciem HTML/CSS (Tailwind) i JavaScript.

Warstwa logiki aplikacji (backend) – zaimplementowana w Pythonie przy użyciu frameworka Django. Obsługuje logikę biznesową, uwierzytelnianie, kontrolery playlist, utworów, użytkowników.

Warstwa danych – relacyjna baza danych PostgreSQL, przechowująca dane o użytkownikach, utworach i playlistach.

System komunikuje się przez REST API z użyciem JSON.

### 9.2 Technologie implementacji systemu
| Technologia   | Zastosowanie                          | Uzasadnienie                                                  |
|---------------|----------------------------------------|---------------------------------------------------------------|
| Python        | Backend (Django)                       | Popularny, elastyczny, szybki w prototypowaniu               |
| Django        | Framework webowy                       | Ułatwia szybkie tworzenie backendu aplikacji                 |
| PostgreSQL    | System zarządzania bazą danych         | Stabilny i skalowalny silnik relacyjny                       |
| Tailwind CSS  | Stylowanie interfejsu użytkownika      | Szybkie prototypowanie i nowoczesny wygląd                   |
| HTML5/CSS3    | Struktura i stylowanie strony          | Standardowe technologie webowe                               |
| JavaScript    | Interaktywność frontendu               | Obsługa dynamicznych akcji na stronie                        |
| GitHub        | Kontrola wersji i współpraca zespołowa | Ułatwia śledzenie zmian i współpracę                         |

### 9.3 Diagramy UML

#### 9.3.1 Diagram(-y) klas

![image](https://github.com/user-attachments/assets/56c98618-0304-4a2e-af00-352471787f64)


#### 9.3.2 Diagram(-y) czynności
##### Tworzenie playlisty
![image](https://github.com/user-attachments/assets/13b6721f-fcff-486f-ab66-e492fd1fd222)
<br>
##### Odtwarzanie utworu
![image](https://github.com/user-attachments/assets/bbc3c397-0cc6-4230-9fbb-b86a43b07394)


#### 9.3.3 Diagramy sekwencji

![image](https://github.com/user-attachments/assets/68622b03-cfcc-428a-91bc-346f595f13d5)

### 9.4 Charakterystyka zastosowanych wzorców projektowych
W systemie Yfitsop zastosowano dwa klasyczne wzorce projektowe:

MVC (Model-View-Controller) – realizowany przez framework Django:

Model – definicje obiektów (Track, Playlist, User),

View – logika przetwarzania żądań HTTP i renderowanie stron,

Controller – pośrednio realizowany przez View/URL routing.

Singleton – dla klasy zarządzającej konfiguracją systemu (np. dostęp do API lub odtwarzacza).

Wzorce te umożliwiają lepszą separację odpowiedzialności oraz łatwiejsze testowanie komponentów.

### 9.5 Projekt Bazy danych

Główne tabele:

#### Tabela: users

| Kolumna     | Typ danych   | NULL     | Klucz       | Opis                          |
|-------------|--------------|----------|-------------|-------------------------------|
| id          | INTEGER      | NOT NULL | PRIMARY KEY | Unikalny identyfikator użytkownika |
| username    | VARCHAR      | NOT NULL | UNIQUE      | Nazwa użytkownika             |
| email       | VARCHAR      | NOT NULL | UNIQUE      | Adres e-mail użytkownika      |
| password    | VARCHAR      | NOT NULL |             | Zaszyfrowane hasło            |
| date_joined | TIMESTAMP    | NOT NULL |             | Data rejestracji              |

---

#### Tabela: tracks

| Kolumna  | Typ danych   | NULL     | Klucz       | Opis                       |
|----------|--------------|----------|-------------|----------------------------|
| id       | INTEGER      | NOT NULL | PRIMARY KEY | Unikalny identyfikator utworu |
| title    | VARCHAR      | NOT NULL |             | Tytuł utworu               |
| artist   | VARCHAR      | NOT NULL |             | Wykonawca                  |
| album    | VARCHAR      | YES      |             | Album                      |
| duration | INTEGER      | NOT NULL |             | Czas trwania w sekundach   |

---

#### Tabela: playlists

| Kolumna | Typ danych | NULL     | Klucz       | Opis                            |
|---------|------------|----------|-------------|---------------------------------|
| id      | INTEGER    | NOT NULL | PRIMARY KEY | Unikalny identyfikator playlisty |
| name    | VARCHAR    | NOT NULL |             | Nazwa playlisty                 |
| user_id | INTEGER    | NOT NULL | FOREIGN KEY | Odniesienie do `users(id)`      |

---

#### Tabela: playlist_tracks

| Kolumna      | Typ danych | NULL     | Klucz       | Opis                             |
|--------------|------------|----------|-------------|----------------------------------|
| playlist_id  | INTEGER    | NOT NULL | FOREIGN KEY | Odniesienie do `playlists(id)`  |
| track_id     | INTEGER    | NOT NULL | FOREIGN KEY | Odniesienie do `tracks(id)`     |

---

## 10 Podsumowanie

Dokumentacja ma na celu przedstawienie szczegółów dotyczących systemu Yfitsop. Dzięki tej dokumentacji, zespół projektowy będzie w stanie wykonać aplikację zgodnie z wymaganiami i terminami.

---

## 11 Szczegółowe nakłady projektowe członków zespołu

| *Członek* | *Zakres prac* | *Czas pracy* |
|-------------|-----------------|----------------|
| Piotr Piotrowski |  |  |
| Dorian Sobierański |  |  |

---

## 12 Inne informacje

Na tym etapie dokumentacja kończy projektowanie i przystępuje do fazy implementacji.
