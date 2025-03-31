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
3. [Wprowadzenie](#wprowadzenie)
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
    2. [Ocena ryzyka](#ocena-ryzyka)
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

Tutaj same diagramy – bez specyfikacji, ale każdy diagram z tytułem i na osobnej stronie.

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

Diagram przedstawiający architekturę systemu: warstwa frontend, backend, baza danych.

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
