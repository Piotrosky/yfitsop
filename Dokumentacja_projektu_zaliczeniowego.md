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

1. [Odnośniki do innych źródeł](#1-odnośniki-do-innych-źródeł)
2. [Słownik pojęć](#2-słownik-pojęć)
3. [Wprowadzenie](#3-wprowadzenie)
    1. [Cel dokumentacji](#3.1-cel-dokumentacji)
    2. [Przeznaczenie dokumentacji](#3.2-przeznaczenie-dokumentacji)
    3. [Opis organizacji lub analiza rynku](#3.3-opis-organizacji-lub-analiza-rynku)
    4. [Analiza SWOT organizacji](#3.4-analiza-swot-organizacji)
4. [Specyfikacja wymagań](#4-specyfikacja-wymagań)
    1. [Charakterystyka ogólna](#4.1-charakterystyka-ogólna)
    2. [Wymagania funkcjonalne](#4.2-wymagania-funkcjonalne)
    3. [Wymagania niefunkcjonalne](#4.3-wymagania-niefunkcjonalne)
5. [Zarządzanie projektem](#5-zarządzanie-projektem)
    1. [Zasoby ludzkie](#5.1-zasoby-ludzkie)
    2. [Harmonogram prac](#5.2-harmonogram-prac)
    3. [Etapy/kamienie milowe projektu](#5.3-etapykamienie-milowe-projektu)
6. [Zarządzanie ryzykiem](#6-zarządzanie-ryzykiem)
    1. [Lista czynników ryzyka](#6.1-lista-czynników-ryzyka)
    2. [Ocena ryzyka](#6.2-ocena-ryzyka)
    3. [Plan reakcji na ryzyko](#6.3-plan-reakcji-na-ryzyko)
7. [Zarządzanie jakością](#7-zarządzanie-jakością)
    1. [Scenariusze i przypadki testowe](#7.1-scenariusze-i-przypadki-testowe)
8. [Projekt techniczny](#8-projekt-techniczny)
    1. [Opis architektury systemu](#8.1-opis-architektury-systemu)
    2. [Technologie implementacji systemu](#8.2-technologie-implementacji-systemu)
    3. [Diagramy UML](#8.3-diagramy-uml)
    4. [Charakterystyka zastosowanych wzorców projektowych](#8.4-charakterystyka-zastosowanych-wzorców-projektowych)
    5. [Projekt bazy danych](#8.5-projekt-bazy-danych)
    6. [Projekt interfejsu użytkownika](#8.6-projekt-interfejsu-użytkownika)
    7. [Procedura wdrożenia](#8.7-procedura-wdrożenia)
9. [Dokumentacja dla użytkownika](#9-dokumentacja-dla-użytkownika)
10. [Podsumowanie](#10-podsumowanie)
11. [Szczegółowe nakłady projektowe członków zespołu](#11-szczegółowe-nakłady-projektowe-członków-zespołu)
12. [Inne informacje](#12-inne-informacje)

---

## 1 Odnośniki do innych źródeł

- *Zarządzanie projektem*: Jira, Trello, itp.
- *Wersjonowanie kodu*: Git (hosting np. na Bitbucket lub Github), ew. SVN
- *System obsługi defektów*: np. Bitbucket, Github, Bugzilla.

---

## 2 Słownik pojęć

Tabela lub lista z pojęciami, które wymagają wyjaśnienia, wraz z tymi wyjaśnieniami – w szczególności synonimy różnych pojęć używanych w dokumentacji.

---

## 3 Wprowadzenie

### 3.1 Cel dokumentacji

Celem dokumentacji jest przedstawienie szczegółowych informacji dotyczących systemu Yfitsop, w tym jego specyfikacji, wymagań funkcjonalnych i niefunkcjonalnych, technologii implementacji oraz zarządzania projektem.

### 3.2 Przeznaczenie dokumentacji

Dokumentacja jest przeznaczona dla zespołu projektowego, przyszłych deweloperów oraz użytkowników systemu.

### 3.3 Opis organizacji lub analiza rynku

Klon Spotify w Django ma na celu dostarczenie prostego, samodzielnie hostowanego rozwiązania do odtwarzania muzyki, skierowanego do:

Małych firm (np. lokalne kawiarnie, sklepy) – jako wewnętrzny system muzyczny.
Entuzjastów technologii – którzy chcą zrozumieć działanie platform streamingowych.
Niszowych twórców muzyki – jako alternatywa dla komercyjnych platform.
Potencjalni użytkownicy:

Liczba organizacji: Tysiące małych firm (np. gastronomia, fitness) mogą potrzebować własnego systemu audio.

Użytkownicy indywidualni: Programiści uczący się Django, hobbyści.
Jednorodność grupy: Różnorodne potrzeby – od edukacyjnych po komercyjne.
Trendy rynkowe:

Wzrost zapotrzebowania na lokalne rozwiązania chmurowce (np. self-hosted alternatywy dla Spotify).
Rosnąca popularność frameworków Pythonowych (Django, FastAPI).

### 3.4 Analiza SWOT organizacji

| *Silne strony* | *Słabe strony* |
|------------------|------------------|
| Niski koszt wdrożenia (open-source)       | Brak skalowalności jak Spotify (np. brak CDN).      |
|Możliwość modyfikacji kodu | Ograniczona funkcjonalność (brak rekomendacji AI) |
| Integracja z istniejącymi bibliotekami audio | Wymaga wiedzy technicznej do hostowania |

| *Szanse*       | *Zagrożenia*   |
|----------------|----------------|
| Rosnący rynek self-hosted tools       | Konkurencja z API (np. Spotify Web API)|
|Możliwość rozszerzenia o płatne funkcje (np. subskrypcje) | Prawo autorskie (problemy z udostępnianiem muzyki) |

---

## 4 Specyfikacja wymagań

### 4.1 Charakterystyka ogólna

#### 4.1.1 Definicja produktu

Yfitsop to aplikacja webowa typu Spotify-clone, umożliwiająca strumieniowe odtwarzanie muzyki. Projekt wykorzystuje technologie Python (Django) i TailwindCSS.

#### 4.1.2 Podstawowe założenia

- Przeglądanie dostępnej biblioteki muzycznej
- Wyszukiwanie utworów według nazwy
- Tworzenie i zarządzanie playlistami
- Odtwarzanie utworów w interfejsie webowym

#### 4.1.3 Cel biznesowy

Celem jest stworzenie platformy do streamingu muzyki jako baza do dalszego rozwoju oraz nauki technologii webowych.

#### 4.1.4 Użytkownicy

- *Zarejestrowani użytkownicy*: Mogą odtwarzać muzykę i zarządzać playlistami.
- *Administratorzy*: Mają dostęp do zarządzania treścią.

#### 4.1.5 Korzyści z systemu

- K-001: Użytkownicy mogą słuchać muzyki online.
- K-002: Użytkownicy mogą wyszukiwać utwory po nazwie.
- K-003: Użytkownicy mogą tworzyć i zarządzać playlistami.
- K-004: Administratorzy mogą dodawać nowe utwory do bazy danych.

#### 4.1.6 Ograniczenia projektowe i wdrożeniowe

- *Backend*: Python (Django)
- *Frontend*: CSS, HTML, JavaScript
- *Baza danych*: SQLite
- *Przeglądarki*: Chrome, Firefox, Edge

Brak możliwości uploadu plików i rekomendacji. Dane użytkowników zgodne z polityką RODO.

### 4.2 Wymagania funkcjonalne

#### 4.2.1 Lista wymagań

- *Odtwarzanie muzyki*: Użytkownik może odtwarzać muzykę za pomocą odtwarzacza.
- *Tworzenie playlisty*: Użytkownik może tworzyć i zarządzać playlistami.
- *Wyszukiwanie utworów*: Użytkownik może wyszukiwać utwory po nazwie, artyście, albumie.
- *Zarządzanie kontem*: Rejestracja, logowanie, zmiana danych użytkownika.

#### 4.2.2 Diagramy przypadków użycia

![image](https://github.com/user-attachments/assets/7430ccb3-5fb9-4f6c-a045-7e1c9e604690)

#### 4.2.3 Szczegółowy opis wymagań

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

*Numer (ID)*: F-003  
*Nazwa*: Rejestracja na platformie
*Uzasadnienie biznesowe*: K-003:  
*Użytkownicy*: Rejestrujący się użytkownicy 
*Scenariusz*: Tworzenie nowego konta 

---

## 5 Zarządzanie projektem

### 5.1 Zasoby ludzkie

Założenie, że projekt byłby realizowany w całości jako projekt komercyjny.

### 5.2 Harmonogram prac

Wskazać czasy trwania poszczególnych etapów i zadań – wykres Gantta.

### 5.3 Etapy/kamienie milowe projektu

1. Faza wstępna: Określenie wymagań, wybór technologii
2. Faza projektowania: Stworzenie schematów UML, projektowanie interfejsu
3. Faza implementacji: Programowanie
4. Faza testowania: Testowanie aplikacji
5. Faza wdrożenia: Wdrożenie aplikacji na serwer

---

## 6 Zarządzanie ryzykiem

### 6.1 Lista czynników ryzyka

1. Niska jakość kodu, brak testów.
2. Ograniczona wiedza z zakresu wybranej technologii.
3. Możliwość opóźnienia w harmonogramie.

### 6.2 Ocena ryzyka

| *Czynnik* | *Prawdopodobieństwo* | *Skala wpływu* | *Ocena ryzyka* |
|-------------|-----------------------|------------------|------------------|
| Brak czasu | 7 | 10 | 11 |

### 6.3 Plan reakcji na ryzyko

Plan reakcji w przypadku wystąpienia opóźnień w harmonogramie – dodatkowe godziny pracy, pomoc z zewnątrz.

---

## 7 Zarządzanie jakością

### 7.1 Scenariusze i przypadki testowe

## Scenariusz testowy #1: Odtwrzanie utworu

### Informacje podstawowe
| Pole | Wartość |
|------|---------|
| **ID** | TC-001 |
| **Nazwa** | Odtwarzanie wybranego utworu |
| **Kategoria** | Test funkcjonalny (UI + Backend) |
| **Opis** | Weryfikacja poprawnego odtwarzania pliku audio |
| **Tester** | Marek Towarek |

## Scenariusz testowy #2: Tworzenie playlisty

### Informacje podstawowe
| Pole | Wartość |
|------|---------|
| **ID** | TC-002 |
| **Nazwa** | Dodawanie nowej playlisty |
| **Kategoria** | Test funkcjonalny (Formularze + DB) |
| **Opis** | Weryfikacja zapisu playlisty do bazy |
| **Tester** | Kamil Adrian Tumulec |
  
---

## 8 Projekt techniczny

### 8.1 Opis architektury systemu

System Yfitsop oparty jest na architekturze trójwarstwowej:

Warstwa prezentacji (frontend) – odpowiedzialna za interakcję z użytkownikiem, zbudowana z użyciem HTML/CSS (Tailwind) i JavaScript.

Warstwa logiki aplikacji (backend) – zaimplementowana w Pythonie przy użyciu frameworka Django. Obsługuje logikę biznesową, uwierzytelnianie, kontrolery playlist, utworów, użytkowników.

Warstwa danych – relacyjna baza danych PostgreSQL, przechowująca dane o użytkownikach, utworach i playlistach.

System komunikuje się przez REST API z użyciem JSON.

### 8.2 Technologie implementacji systemu
| Technologia   | Zastosowanie                          | Uzasadnienie                                                  |
|---------------|----------------------------------------|---------------------------------------------------------------|
| Python        | Backend (Django)                       | Popularny, elastyczny, szybki w prototypowaniu               |
| Django        | Framework webowy                       | Ułatwia szybkie tworzenie backendu aplikacji                 |
| SQLite    | System zarządzania bazą danych         | Stabilny i skalowalny silnik relacyjny                       |
| CSS  | Stylowanie interfejsu użytkownika      | Szybkie prototypowanie i nowoczesny wygląd                   |
| HTML5/CSS3    | Struktura i stylowanie strony          | Standardowe technologie webowe                               |
| JavaScript    | Interaktywność frontendu               | Obsługa dynamicznych akcji na stronie                        |
| GitHub        | Kontrola wersji i współpraca zespołowa | Ułatwia śledzenie zmian i współpracę                         |

### 8.3 Diagramy

#### 8.3.1 Diagram(-y) klas

![image](https://github.com/user-attachments/assets/56c98618-0304-4a2e-af00-352471787f64)


#### 8.3.2 Diagram(-y) czynności
##### Tworzenie playlisty
![image](https://github.com/user-attachments/assets/13b6721f-fcff-486f-ab66-e492fd1fd222)
<br>
##### Odtwarzanie utworu
![image](https://github.com/user-attachments/assets/bbc3c397-0cc6-4230-9fbb-b86a43b07394)


#### 8.3.3 Diagramy sekwencji

![image](https://github.com/user-attachments/assets/68622b03-cfcc-428a-91bc-346f595f13d5)

![image](https://github.com/user-attachments/assets/239ef84c-6800-42b6-9175-b217377ac83e)

![image](https://github.com/user-attachments/assets/e04a761d-2790-4f94-859a-4c67a06205a1)

![image](https://github.com/user-attachments/assets/5754beb1-b85f-47d5-ab42-5c758ee2e61f)

![image](https://github.com/user-attachments/assets/f9197575-1e65-4636-9b31-75faec693747)



### 8.4 Charakterystyka zastosowanych wzorców projektowych
W systemie Yfitsop zastosowano dwa klasyczne wzorce projektowe:

MVC (Model-View-Controller) – realizowany przez framework Django:

Model – definicje obiektów (Track, Playlist, User),

View – logika przetwarzania żądań HTTP i renderowanie stron,

Controller – pośrednio realizowany przez View/URL routing.

Singleton – dla klasy zarządzającej konfiguracją systemu (np. dostęp do API lub odtwarzacza).

Wzorce te umożliwiają lepszą separację odpowiedzialności oraz łatwiejsze testowanie komponentów.

### 8.5 Projekt Bazy danych

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

## Kluczowe osiągnięcia projektu
- Stworzenie funkcjonalnego prototypu aplikacji streamingowej z wykorzystaniem:
  - Django (backend)
  - TailwindCSS (frontend)
- Kompletna architektura systemu oparta o wzorzec MVC
- Podstawowe funkcjonalności:
  - Odtwarzanie muzyki
  - Tworzenie playlist
  - Wyszukiwanie utworów
- Szczegółowa dokumentacja:
  - Techniczna
  - Testowa

## Napotkane wyzwania
| Wyzwanie | Sposób rozwiązania |
|----------|-------------------|
| Ograniczenia czasowe | Priorytetyzacja funkcji |
| Ograniczone możliwości techniczne | Wybór sprawdzonych technologii |
| Zapewnienie jakości kodu | Implementacja testów |

## Perspektywy rozwoju
1. **Rozszerzenie funkcjonalności**:
   - System rekomendacji utworów
   - Udostępnianie playlist
2. **Rozwój techniczny**:
   - Wsparcie dodatkowych formatów audio
   - Poprawa skalowalności systemu
3. **Wdrożeniowe**:
   - Optymalizacja pod kątem większej liczby użytkowników

## Podsumowanie końcowe
Projekt Yfitsop stanowi udaną implementację podstawowych mechanizmów platformy streamingowej i może służyć jako:
- Baza do dalszego rozwoju
- Materiał edukacyjny
- Punkt wyjścia dla komercyjnych rozwiązań

Dokumentacja zawiera wszystkie niezbędne elementy pozwalające na kontynuację prac nad systemem.

---

## 11 Szczegółowe nakłady projektowe członków zespołu

| *Członek* | *Zakres prac* | *Czas pracy* |
|-------------|-----------------|----------------|
| Piotr Piotrowski | 50% | 15h |
| Dorian Sobierański | 50% | 15h |

---

## 12 Inne informacje

Na tym etapie dokumentacja kończy projektowanie i przystępuje do fazy implementacji.
