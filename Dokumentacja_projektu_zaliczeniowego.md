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

## 1 Spis Treści

2. [Odnośniki do innych źródeł](#2-odnośniki-do-innych-źródeł)
3. [Słownik pojęć](#3-słownik-pojęć)
4. [Wprowadzenie](#4-wprowadzenie)
    1. [Cel dokumentacji](#4.1-cel-dokumentacji)
    2. [Przeznaczenie dokumentacji](#4.2-przeznaczenie-dokumentacji)
    3. [Opis organizacji lub analiza rynku](#4.3-opis-organizacji-lub-analiza-rynku)
    4. [Analiza SWOT organizacji](#4.4-analiza-swot-organizacji)
5. [Specyfikacja wymagań](#5-specyfikacja-wymagań)
    1. [Charakterystyka ogólna](#5.1-charakterystyka-ogólna)
    2. [Wymagania funkcjonalne](#5.2-wymagania-funkcjonalne)
    3. [Wymagania niefunkcjonalne](#5.3-wymagania-niefunkcjonalne)
6. [Zarządzanie projektem](#6-zarządzanie-projektem)
    1. [Zasoby ludzkie](#6.1-zasoby-ludzkie)
    2. [Harmonogram prac](#6.2-harmonogram-prac)
    3. [Etapy/kamienie milowe projektu](#6.3-etapykamienie-milowe-projektu)
7. [Zarządzanie ryzykiem](#7-zarządzanie-ryzykiem)
    1. [Lista czynników ryzyka](#7.1-lista-czynników-ryzyka)
    2. [Ocena ryzyka](#7.2-ocena-ryzyka)
    3. [Plan reakcji na ryzyko](#7.3-plan-reakcji-na-ryzyko)
8. [Zarządzanie jakością](#8-zarządzanie-jakością)
    1. [Scenariusze i przypadki testowe](#8.1-scenariusze-i-przypadki-testowe)
9. [Projekt techniczny](#9-projekt-techniczny)
    1. [Opis architektury systemu](#9.1-opis-architektury-systemu)
    2. [Technologie implementacji systemu](#9.2-technologie-implementacji-systemu)
    3. [Diagramy UML](#9.3-diagramy-uml)
    4. [Charakterystyka zastosowanych wzorców projektowych](#9.4-charakterystyka-zastosowanych-wzorców-projektowych)
    5. [Projekt bazy danych](#9.5-projekt-bazy-danych)
    6. [Projekt interfejsu użytkownika](#9.6-projekt-interfejsu-użytkownika)
    7. [Procedura wdrożenia](#9.7-procedura-wdrożenia)
10. [Dokumentacja dla użytkownika](#10-dokumentacja-dla-użytkownika)
11. [Podsumowanie](#11-podsumowanie)
    1.[Szczegółowe nakłady projektowe członków zespołu](#11.1-szczegółowe-nakłady-projektowe-członków-zespołu)
12. [Inne informacje](#12-inne-informacje)

---

## 2. Odnośniki do innych źródeł

- **Zarządzanie projektem**:  
  Projekt był zarządzany przy użyciu narzędzi takich jak [Jira](https://www.atlassian.com/software/jira) oraz [Trello](https://trello.com/), które umożliwiały planowanie zadań, podział pracy oraz monitorowanie postępu.

- **Wersjonowanie kodu**:  
  Wersjonowanie kodu odbywało się z wykorzystaniem systemu kontroli wersji Git. Hosting projektu znajdował się na platformie [GitHub](https://github.com/) oraz opcjonalnie [Bitbucket](https://bitbucket.org/).

- **System obsługi defektów**:  
  Do raportowania i śledzenia błędów używano systemów takich jak GitHub Issues oraz [Bugzilla](https://www.bugzilla.org/) – zapewniało to przejrzystość oraz możliwość przypisywania zgłoszeń do odpowiednich członków zespołu.

---

## 3. Słownik pojęć

| Pojęcie                | Wyjaśnienie |
|------------------------|-------------|
| **Utwór**              | Plik audio przechowywany w bazie danych systemu, możliwy do odtworzenia przez użytkownika. |
| **Playlista**          | Lista utworów utworzona przez użytkownika, zapisana w bazie danych; może zawierać dowolną liczbę utworów. |
| **Frontend**           | Część aplikacji widoczna dla użytkownika – interfejs graficzny (UI), stworzony np. w HTML/CSS/JS lub z użyciem frameworka. |
| **Backend**            | Logika aplikacji i warstwa komunikacji z bazą danych, przetwarzanie żądań, uwierzytelnianie itd. |
| **Baza danych (DB)**   | Miejsce przechowywania wszystkich danych użytkownika i aplikacji (np. utworów, playlist, kont użytkowników). |
| **Hashowanie**         | Proces przekształcania danych (np. hasła) do postaci nieodwracalnej, zabezpieczającej je przed kradzieżą. |
| **CAPTCHA**            | Mechanizm zabezpieczający logowanie przed automatycznymi botami. |
| **SQL Injection**      | Atak polegający na wstrzyknięciu złośliwego zapytania SQL – należy się przed nim zabezpieczać. |
| **Sesja użytkownika**  | Okres aktywności użytkownika w aplikacji – kontrolowany poprzez tokeny lub pliki cookie. |
| **Test jednostkowy**   | Automatyczny test sprawdzający poprawność działania pojedynczej funkcji lub metody. |
| **Użyteczność (usability)** | Łatwość korzystania z aplikacji przez końcowego użytkownika. Mierzona często czasem potrzebnym do wykonania konkretnej czynności. |

---

## 4 Wprowadzenie

### 4.1 Cel dokumentacji

Celem dokumentacji jest przedstawienie szczegółowych informacji dotyczących systemu Yfitsop, w tym jego specyfikacji, wymagań funkcjonalnych i niefunkcjonalnych, technologii implementacji oraz zarządzania projektem.

### 4.2 Przeznaczenie dokumentacji

Dokumentacja jest przeznaczona dla zespołu projektowego, przyszłych deweloperów oraz użytkowników systemu.

### 4.3 Opis organizacji i analiza rynku

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

### 4.4 Analiza SWOT organizacji

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
- *Frontend*: CSS, HTML, JavaScript
- *Baza danych*: SQLite
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

*Numer (ID)*: F-003  
*Nazwa*: Rejestracja na platformie
*Uzasadnienie biznesowe*: K-003:  
*Użytkownicy*: Rejestrujący się użytkownicy 
*Scenariusz*: Tworzenie nowego konta 

### 5.3 Wymagania niefunkcjonalne  
W odniesieniu do całego systemu, modułów lub innych składowych systemu:

#### 1. Wydajność  
- System powinien uruchamiać się w czasie nie dłuższym niż 3 sekundy na komputerze klasy użytkowej (min. 8 GB RAM, SSD).  
- Czas rozpoczęcia odtwarzania utworu po kliknięciu nie może przekroczyć 500 ms.  
- Wyszukiwanie utworów w bazie (do 10 000 rekordów) nie powinno przekraczać 300 ms.  

#### 2. Bezpieczeństwo  
- Dane użytkownika (w tym hasła) muszą być przechowywane z użyciem bezpiecznego algorytmu hashującego (np. bcrypt).  
- System nie może pozwolić na wykonanie zapytań typu SQL Injection, XSS, ani CSRF.  
- Regularne kopie zapasowe bazy danych (min. raz na 24h) w celu zapobiegania trwałej utracie danych.  
- W razie awarii, system powinien umożliwić odtworzenie danych z kopii w ciągu 2 godzin.  

#### 3. Zabezpieczenia  
- Logowanie powinno być zabezpieczone przez CAPTCHA po 3 nieudanych próbach.  
- Sesja użytkownika wygasa po 30 minutach braku aktywności.  
- Aplikacja nie powinna mieć dostępu do zasobów systemowych użytkownika poza katalogiem aplikacji.  
- Wszystkie operacje użytkownika powinny być rejestrowane w logach (np. tworzenie playlist, odtwarzanie utworu, logowanie).  

#### 4. Inne cechy jakości  
- **Dostępność**: 99,5% czasu działania miesięcznie przy wdrożeniu produkcyjnym.  
- **Testowalność**: pokrycie kodu testami jednostkowymi na poziomie minimum 80%.  
- **Użyteczność**: nowy użytkownik powinien być w stanie utworzyć playlistę i dodać utwór w czasie krótszym niż 2 minuty.  
- **Przenośność**: aplikacja powinna działać zarówno na Windows 10+, macOS oraz systemach Linux (np. Ubuntu 22.04).  
- **Łatwość konserwacji**: kod podzielony na moduły, z dokumentacją techniczną oraz komentarzami w kluczowych miejscach.  
- **Adaptowalność**: system umożliwia integrację z zewnętrznymi serwisami API do pobierania metadanych o utworach.  
- **Awaryjność**: maksymalna liczba nieplanowanych przerw w działaniu systemu – nie więcej niż 1 dziennie.  
- **Poprawność**: każda akcja użytkownika powinna skutkować jednoznaczną odpowiedzią systemu (np. komunikatem lub reakcją UI).  
- **Elastyczność**: możliwa edycja szaty graficznej przez zmianę plików stylów (CSS/Theme) bez ingerencji w logikę działania.


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
| Brak czasu | 7 | 10 | 11 |

### 7.3 Plan reakcji na ryzyko

Plan reakcji w przypadku wystąpienia opóźnień w harmonogramie – dodatkowe godziny pracy, pomoc z zewnątrz.

---

## 8 Zarządzanie jakością

### 8.1 Scenariusze i przypadki testowe

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

##Scenariusz testowy #3: Usuwanie utworu z playlisty

### Informacje podstawowe
| Pole          | Wartość                                                                                    |
| ------------- | ------------------------------------------------------------------------------------------ |
| **ID**        | TC-003                                                                                     |
| **Nazwa**     | Usuwanie utworu z playlisty                                                                |
| **Kategoria** | Test funkcjonalny (UI + Backend + DB)                                                      |
| **Opis**      | Weryfikacja poprawnego usunięcia utworu z istniejącej playlisty i aktualizacji bazy danych |
| **Tester**    | Anna Nowak                                                                                 |



##Scenariusz testowy #4: Wyszukiwanie utworów

### Informacje podstawowe
| Pole          | Wartość                                                                       |
| ------------- | ----------------------------------------------------------------------------- |
| **ID**        | TC-004                                                                        |
| **Nazwa**     | Wyszukiwanie utworów według tytułu i artysty                                  |
| **Kategoria** | Test funkcjonalny (UI + Backend)                                              |
| **Opis**      | Weryfikacja poprawności działania mechanizmu wyszukiwania utworów w aplikacji |
| **Tester**    | Piotr Kaczmarek                                                               |



##Scenariusz testowy #5: Edycja szczegółów playlisty

### Informacje podstawowe
| Pole          | Wartość                                                                                             |
| ------------- | --------------------------------------------------------------------------------------------------- |
| **ID**        | TC-005                                                                                              |
| **Nazwa**     | Edycja nazwy i opisu playlisty                                                                      |
| **Kategoria** | Test funkcjonalny (Formularze + DB)                                                                 |
| **Opis**      | Sprawdzenie poprawności edycji nazwy i opisu istniejącej playlisty oraz aktualizacji w bazie danych |
| **Tester**    | Magdalena Lis                                                                                       |





##Scenariusz testowy #6: Odtwarzanie losowe (shuffle)

### Informacje podstawowe
| Pole          | Wartość                                                                 |
| ------------- | ----------------------------------------------------------------------- |
| **ID**        | TC-006                                                                  |
| **Nazwa**     | Odtwarzanie losowe utworów z playlisty                                  |
| **Kategoria** | Test funkcjonalny (UI + Backend)                                        |
| **Opis**      | Weryfikacja działania trybu odtwarzania losowego na wybranej playliście |
| **Tester**    | Tomasz Zieliński                                                        |




##Scenariusz testowy #7: Logowanie użytkownika

### Informacje podstawowe
| Pole          | Wartość                                                                           |
| ------------- | --------------------------------------------------------------------------------- |
| **ID**        | TC-007                                                                            |
| **Nazwa**     | Logowanie do aplikacji                                                            |
| **Kategoria** | Test funkcjonalny (UI + Backend + Security)                                       |
| **Opis**      | Sprawdzenie poprawności procesu logowania z prawidłowymi i nieprawidłowymi danymi |
| **Tester**    | Katarzyna Woźniak                                                                 |


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
| SQLite    | System zarządzania bazą danych         | Stabilny i skalowalny silnik relacyjny                       |
| CSS  | Stylowanie interfejsu użytkownika      | Szybkie prototypowanie i nowoczesny wygląd                   |
| HTML5/CSS3    | Struktura i stylowanie strony          | Standardowe technologie webowe                               |
| JavaScript    | Interaktywność frontendu               | Obsługa dynamicznych akcji na stronie                        |
| GitHub        | Kontrola wersji i współpraca zespołowa | Ułatwia śledzenie zmian i współpracę                         |

### 9.3 Diagramy

#### 9.3.1 Diagram(-y) klas

![image](https://github.com/user-attachments/assets/56c98618-0304-4a2e-af00-352471787f64)


#### 9.3.2 Diagram(-y) czynności
##### Tworzenie playlisty
![image](https://github.com/user-attachments/assets/13b6721f-fcff-486f-ab66-e492fd1fd222)
<br>
##### Odtwarzanie utworu
![image](https://github.com/user-attachments/assets/bbc3c397-0cc6-4230-9fbb-b86a43b07394)


#### 9.3.3 Diagramy sekwencji

##### Użytkownik tworzy playliste
![image](https://github.com/user-attachments/assets/68622b03-cfcc-428a-91bc-346f595f13d5)
##### Użytkownik usuwa utwór z polubionych
![image](https://github.com/user-attachments/assets/239ef84c-6800-42b6-9175-b217377ac83e)
##### Użytkownik wyszukuje utwór w playliście
![image](https://github.com/user-attachments/assets/e04a761d-2790-4f94-859a-4c67a06205a1)
##### Użytkownik dodaje utwór do playlisty
![image](https://github.com/user-attachments/assets/5754beb1-b85f-47d5-ab42-5c758ee2e61f)
##### Użytkownik rejestruje się w aplikacji
![image](https://github.com/user-attachments/assets/f9197575-1e65-4636-9b31-75faec693747)



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
### 9.6 Projekt interfejsu użytkownika
![Untitled](https://github.com/user-attachments/assets/1275002c-29e5-4a22-be00-31f5f636d460)
![Untitled](https://github.com/user-attachments/assets/b0f4a23b-6255-4a6a-85a8-37bd1001254d)
![Untitled](https://github.com/user-attachments/assets/e1a5d06e-d02c-4fc4-958c-1e56421156a0)
![Untitled](https://github.com/user-attachments/assets/9d2d6bfa-b0e3-4dba-bc36-c9a336d36cc1)
![Untitled](https://github.com/user-attachments/assets/1d4194c8-3e81-4fd9-8b81-d36d651b8dac)



## 11 Podsumowanie

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

### 11.1 Szczegółowe nakłady projektowe członków zespołu

| *Członek* | *Zakres prac* | *Czas pracy* |
|-------------|-----------------|----------------|
| Piotr Piotrowski | 50% | 15h |
| Dorian Sobierański | 50% | 15h |

---

## 12 Inne informacje

Na tym etapie dokumentacja kończy projektowanie i przystępuje do fazy implementacji.
