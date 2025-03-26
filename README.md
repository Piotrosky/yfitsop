Dokumentacja projektu zaliczeniowego
Przedmiot: Inżynieria oprogramowania

Temat:	Aplikacja do streamingu muzyki 
Autorzy:	Piotr Piotrowski i Dorian Sobierański
Grupa:	214A
Kierunek:	informatyka
Rok akademicki:	II
Poziom i semestr:	I/4
Tryb studiów:	stacjonarne


Należy pozostawić wszelkie nagłówki tego dokumentu, a umieszczać treść w odpowiednich miejscach zamiast obecnych objaśnień.
Stronę tytułową można sformatować w dowolny sposób, ale należy pozostawić zawartość informacyjną w układzie pokazanym powyżej.
Praca powinna zostać złożona wyłącznie w formacie pdf. Przed wygenerowaniem ostatecznej wersji należy zaktualizować spis treści – wyświetlane dwa poziomy.
Niniejszą informację należy również usunąć z wersji końcowej.

# Spis Treści

1. [Spis treści](#spis-treści)  
2. [Odnośniki do innych źródeł](#odnośniki-do-innych-źródeł)  
3. [Słownik pojęć](#słownik-pojęć)  
4. [Wprowadzenie](#wprowadzenie)  
   4.1 [Cel dokumentacji](#cel-dokumentacji)  
   4.2 [Przeznaczenie dokumentacji](#przeznaczenie-dokumentacji)  
   4.3 [Opis organizacji lub analiza rynku](#opis-organizacji-lub-analiza-rynku)  
   4.4 [Analiza SWOT organizacji](#analiza-swot-organizacji)  
5. [Specyfikacja wymagań](#specyfikacja-wymagań)  
   - [Charakterystyka ogólna](#charakterystyka-ogólna)  
   - [Wymagania funkcjonalne](#wymagania-funkcjonalne)  
   - [Wymagania niefunkcjonalne](#wymagania-niefunkcjonalne)  
6. [Zarządzanie projektem](#zarządzanie-projektem)  
   - [Zasoby ludzkie](#zasoby-ludzkie)  
   - [Harmonogram prac](#harmonogram-prac)  
   - [Etapy/kamienie milowe projektu](#etapykamienie-milowe-projektu)  
7. [Zarządzanie ryzykiem](#zarządzanie-ryzykiem)  
   - [Lista czynników ryzyka](#lista-czynników-ryzyka)  
   - [Ocena ryzyka](#ocena-ryzyka)  
   - [Plan reakcji na ryzyko](#plan-reakcji-na-ryzyko)  
8. [Zarządzanie jakością](#zarządzanie-jakością)  
   - [Scenariusze i przypadki testowe](#scenariusze-i-przypadki-testowe)  
9. [Projekt techniczny](#projekt-techniczny)  
   - [Opis architektury systemu](#opis-architektury-systemu)  
   - [Technologie implementacji systemu](#technologie-implementacji-systemu)  
   - [Diagramy UML](#diagramy-uml)  
   - [Charakterystyka zastosowanych wzorców projektowych](#charakterystyka-zastosowanych-wzorców-projektowych)  
   - [Projekt bazy danych](#projekt-bazy-danych)  
   - [Projekt interfejsu użytkownika](#projekt-interfejsu-użytkownika)  
   - [Procedura wdrożenia](#procedura-wdrożenia)  
10. [Dokumentacja dla użytkownika](#dokumentacja-dla-użytkownika)  
11. [Podsumowanie](#podsumowanie)  
    - [Szczegółowe nakłady projektowe członków zespołu](#szczegółowe-nakłady-projektowe-członków-zespołu)  
12. [Inne informacje](#inne-informacje)  


# Odnośniki do innych źródeł
2 Odnośniki do innych źródeł
tj. do wykorzystywanych narzędzi / projektów w tych narzędziach
        ◦ Zarządzania projektem – Jira, Trello, itp.
        ◦ Wersjonowanie kodu – sugerowany Git (hosting np. na Bitbucket lub Github), ew. SVN
        ◦ System obsługi defektów – np. Bitbucket, Github, Bugzilla.
# Słownik Pojęć
3 Słownik pojęć
Tabela lub lista z pojęciami, które wymagają wyjaśnienia, wraz z tymi wyjaśnieniami – w szczególności synonimy różnych pojęć używanych w dokumentacji.

# 4. Wprowadzenie
## 4.1 Cel dokumentacji
po co ją robimy i co zawiera (poziom szczegółowości)

## 4.2 Przeznaczenie dokumentacji
dla kogo ona jest
## 4.3 Opis organizacji lub analiza rynku
Jedna z dwóch opcji:
    1. Jeśli dla konkretnej organizacji: Czym jest organizacja, dla której realizowany będzie system; jak działa (lub będzie działała), kiedy system będzie wdrożony – tutaj nie odwołujemy się do samego systemu, tylko opisujemy samo działanie organizacji i role. W szczególności – jak wyglądają główne procesy biznesowe.
    2. Jeśli na masowy rynek: Pobieżna analiza rynku. Dla kogo będzie przydatny taki system. Ile jest organizacji, które będą mogły z niego skorzystać, użytkowników w poszczególnych organizacjach. Czy te organizacje stanowią jednorodną grupę czy są różne rodzaje. Co one mają ze sobą wspólnego. Jak ta liczba będzie się zmieniała w najbliższej przyszłości.
## 4.4 Analiza SWOT organizacji
    • jeśli system dla konkretnej organizacji:
        ◦ wystarczy sama tabela 2x2 (silne-słabe-szanse-zagrożenia)
    • jeśli system na masowy rynek:
        ◦ szanse i zagrożenia
# 5 Specyfikacja wymagań
## 5.1 Charakterystyka ogólna
### 5.1.1 Definicja produktu
Yfitsop to aplikacja webowa typu Spotify-clone, umożliwiająca strumieniowe odtwarzanie muzyki. Projekt został stworzony jako baza do dalszego rozwoju oraz nauki technologii webowych, takich jak Python (Django) i TailwindCSS. 
### 5.1.2 Podstawowe założenia
Yfitsop jest aplikacją webową, która pozwala użytkownikom na:

- Przeglądanie dostępnej biblioteki muzycznej
- Wyszukiwanie utworów według nazwy
- Tworzenie I zarządzanie playlistami
- Odtwarzanie utworów w interfejsie webowym
- Aplikacja nie umożliwia przesyłania własnych utworów ani generowania rekomendacji
### 5.1.3 Cel biznesowy
Celem wdrożenia systemu jest stworzenie prostej platformy do streamingu muzyki, która może być używana jako baza do dalszego rozwoju oraz nauki technologii webowych takich jak Python (Django) i TailwindCSS.
### 5.1.4 Użytkownicy
Zarejestrowani użytkownicy – mogą odtwarzać muzykę i zarządzać swoimi playlistami.
Administratorzy – mają dostęp do zarządzania treścią (np. dodawanie nowych utworów do systemu). 
### 5.1.5 Korzyści z systemu
K-001: Użytkownicy mogą słuchać muzyki online.
K-002: Użytkownicy mogą wyszukiwać utwory po nazwie.
K-003: Użytkownicy mogą tworzyć i zarządzać playlistami.
K-004: Administratorzy mogą dodawać nowe utwory do bazy danych. 
### 5.1.6 Ograniczenia projektowe i wdrożeniowe
Technologie:	
	Backend: Python (Django)
	Frontend: TailwindCSS
	Baza danych: PostgreSQL 

Przeglądarki: Aplikacja będzie zoptymalizowana pod najnowsze wersje Chrome, Firefox i Edge.

Brak możliwości uploadu plików: Użytkownicy nie mogą przesyłać własnej muzyki.

Brak rekomendacji: System nie sugeruje utworów na podstawie historii odtwarzania.

Ochrona danych: Dane użytkowników będą przechowywane zgodnie z polityką RODO. 

5.2 Wymagania funkcjonalne
5.2.1 Lista wymagań
1. **Odtwarzanie muzyki**
Użytkownik może odtwarzać muzykę za pomocą odtwarzacza w aplikacji.
2. **Tworzenie playlisty**
Użytkownik może tworzyć i zarządzać własnymi playlistami.
3. **Wyszukiwanie utworów**
Użytkownik może wyszukiwać utwory po nazwie, artyście lub albumie.
4. **Zarządzanie kontem użytkownika**
Użytkownik może rejestrować się, logować i zarządzać swoim kontem (zmiana danych, hasła).
5. **Dostęp do biblioteki muzycznej**
Użytkownik ma dostęp do pełnej biblioteki muzycznej w aplikacji.

5.2.2 Diagramy przypadków użycia
Tutaj same diagramy – bez specyfikacji, ale każdy diagram z tytułem i na osobnej stronie
5.2.3 Szczegółowy opis wymagań
- Numer (ID): F-001
- Nazwa: Odtwarzanie muzyki
- Uzasadnienie biznesowe:  
  Odwołanie do 5.1.5 Korzyści z systemu:  
  - K-001: Użytkownicy mogą słuchać muzyki online.
 
- Użytkownicy:  
  - Zarejestrowani użytkownicy.
Scenariusz 1: Odtwarzanie wybranego utworu
 
Warunki początkowe:  
  - Użytkownik jest zalogowany.  
  - Użytkownik znajduje się na stronie z listą utworów.
 
Przebieg działań:  
  1. Użytkownik przegląda listę dostępnych utworów.  
  2. Użytkownik wybiera utwór z listy.  
  3. Aplikacja zaczyna odtwarzać wybrany utwór.  
  4. Użytkownik może pauzować, wznawiać lub zmieniać utwór.
 
Efekty (warunki końcowe):  
  - Utwór zaczyna być odtwarzany.  
  - Użytkownik może kontrolować odtwarzanie utworu.

- Numer (ID): F-002
- Nazwa: Tworzenie playlisty
- Uzasadnienie biznesowe:  
  Odwołanie do 5.1.5 Korzyści z systemu:  
  - K-003: Użytkownicy mogą tworzyć i zarządzać playlistami.
 
- Użytkownicy:  
  - Zarejestrowani użytkownicy.
 
Scenariusz 1: Tworzenie nowej playlisty
 
Warunki początkowe:  
  - Użytkownik jest zalogowany.  
  - Użytkownik znajduje się w sekcji "Playlists".
 
Przebieg działań:  
  1. Użytkownik klika przycisk "Nowa playlista".  
  2. Użytkownik wpisuje nazwę playlisty.  
  3. Użytkownik wybiera utwory, które mają znaleźć się w playliście.  
  4. Użytkownik zapisuje playlistę.
 
Efekty (warunki końcowe):  
  - Playlista jest zapisana w systemie i widoczna na liście użytkownika.
5.3 Wymagania niefunkcjonalne
W odniesieniu do całego systemu, modułów lub innych składowych systemu
    1. Wydajność – w odniesieniu do konkretnych sytuacji – funkcji systemu
    2. Bezpieczeństwo – utrata, zniszczenie danych, zniszczenie innego systemu przez nasz – wraz z działaniami zapobiegawczymi i ograniczającymi skutki
    3. Zabezpieczenia
    4. Inne cechy jakości – najlepiej ilościowo, żeby można było zweryfikować (zmierzyć) – adaptowalność, dostępność, poprawność, elastyczność, łatwość konserwacji, przenośność, awaryjność, testowalność, użyteczność
6 Zarządzanie projektem
6.1 Zasoby ludzkie
(rzeczywiste lub hipotetyczne) – przy realizacji projektu
Należy założyć, że projekt byłby realizowany w całości jako projekt komercyjny a nie tylko częściowo w ramach zajęć na uczelni
6.2 Harmonogram prac
Etapy mogą się składać z zadań.
Wskazać czasy trwania poszczególnych etapów i zadań – wykres Gantta.
obejmuje również harmonogram wdrożenia projektu – np. szkolenie, rozruch, konfiguracja, serwis – może obejmować różne wydania (tj. o różnej funkcjonalności – personal, professional, enterprise) i wersje (1.0, 1.5, itd.)
6.3 Etapy/kamienie milowe projektu
dla głównych etapów projektu


W grupach prowadzonych przez ŁR ten cały ten rozdział jest opcjonalny – dla chętnych. Nie jest omawiany na wykładzie!
Studenci powinni skonsultować szczegółowe wymagania w tym zakresie z nauczycielem prowadzącym zajęcia w danej grupie.

7 Zarządzanie ryzykiem
7.1 Lista czynników ryzyka
Wypełniona lista kontrolna
7.2 Ocena ryzyka
prawdopodobieństwo i wpływ
7.3 Plan reakcji na ryzyko
Działania w odniesieniu do poszczególnych ryzyk.
Mogą być wg różnych strategii, tj. kilka strategii dla pojedynczego czynnika ryzyka 


Rozdział obowiązkowy w zespołach co najmniej 3-osobowych, w mniejszych – do uzgodnienia z prowadzącym zajęcia.
8 Zarządzanie jakością
8.1 Scenariusze i przypadki testowe
głównie testowanie funkcjonalności, ale może być też testowanie wymagań niefunkcjonalnych/zgodności; każdy scenariusz od nowej strony, musi zawierać co najmniej następujące informacje (sugerowany układ tabelaryczny, np. wg szablonu podanego w osobnym pliku lub na wykładzie):
    • numer – jako ID
    • nazwa scenariusza – co test w nim testowane (max kilka wyrazów)
    • kategoria – poziom/kategoria testów
    • opis – dodatkowe opcjonalne informacje, które nie zmieściły się w nazwie
    • tester - konkretna osoba lub klient/pracownik,
    • termin – kiedy testowanie ma być przeprowadzane,
    • narzędzia wspomagające – jeśli jakieś są używane przy danym scenariuszu
    • przebieg działań – tabela z trzema kolumnami: lp. oraz opisującymi działania testera i systemu
    • założenia, środowisko, warunki wstępne, dane wejściowe – przygotowanie przed uruchomieniem testów
    • zestaw danych testowych – najlepiej w formie tabelarycznej – jakie konkretnie dane mają być użyte przez testera i zwrócone przez system w poszczególnych krokach przebiegu działań
    • przebieg lub zestaw danych testowych musi zawierać jawną informację o warunku zaliczenia testu
9 Projekt techniczny
9.1 Opis architektury systemu
z ew. rysunkami pomocniczymi
9.2 Technologie implementacji systemu
tabela z listą wykorzystanych technologii, każda z uzasadnieniem
9.3 Diagramy UML
każdy diagram ma mieć tytuł oraz ma być na osobnej stronie
diagramy przypadków użycia umieszczone w punkcie 5.2.2, a nie tutaj.

9.3.1 Diagram(-y) klas
1 lub więcej
9.3.2 Diagram(-y) czynności
Co najmniej 1 dla zespołów 2-osobowych, więcej dla liczniejszych
9.3.3 Diagramy sekwencji
co najmniej 5, w tym co najmniej 1 przypadek użycia zilustrowany kilkoma diagramami (dla zespołów 2-osobowych, dla liczniejszych więcej)
9.3.4 Inne diagramy
co najmniej trzy – komponentów, rozmieszczenia, maszyny stanowej itp.
9.4 Charakterystyka zastosowanych wzorców projektowych
informacja opisowa wspomagana diagramami (odsyłaczami do diagramów UML); jeśli wykorzystano wzorce projektowe, to należy wykazać dwa z nich
uwaga – wzorce projektowe nie są omawiane na wykładach!
9.5 Projekt bazy danych
9.5.1 Schemat
w trzeciej formie normalnej; jeśli w innej to umieć uzasadnić wybór
9.5.2 Projekty szczegółowe tabel
w zależności, czy następujące elementy są widoczne na schemacie b.d.: nazwa tabeli, nazwy pól, typ danych, wartości NULL, klucz główny, klucz obcy –
- jeśli TAK: i nie ma potrzeby pokazania dodatkowych elementów b.d., to ten punkt może być pusty,
- jeśli NIE: to podać te elementy, których nie widać na schemacie.
dodatkowymi elementami mogą być np. triggery, procedury, funkcje, indeksy, użytkownicy, role. 
9.6 Projekt interfejsu użytkownika
co najmniej dla głównej funkcjonalności programu – w razie wątpliwości, uzgodnić z prowadzącym zajęcia
9.6.1 Lista głównych elementów interfejsu
okien, stron, aktywności (Android)
9.6.2 Przejścia między głównymi elementami
np. storyboard, schemat blokowy lub inna notacja
9.6.3 Projekty szczegółowe poszczególnych elementów
dla 5-7 głównych elementów (w zespołach 2-osobowych)
każdy element od nowej strony z następującą minimalną zawartością:
    • numer – ID elementu
    • nazwa – np. formularz danych produktu
    • projekt graficzny – wystarczy schemat w narzędziu graficznym lub zrzut ekranu – z przykładowymi danymi (nie pusty!!!)

    • opcjonalnie:
    • opis – dodatkowe opcjonalne informacje o przeznaczeniu, obsłudze – jeśli nazwa nie będzie wystarczająco czytelna
    • wykorzystane dane – jakie dane z bazy danych są wykorzystywane
    • opis działania – tabela pokazująca m.in. co się dzieje po kliknięciu przycisku, wybraniu opcji z menu itp.
9.7 Procedura wdrożenia
jeśli informacje w harmonogramie nie są wystarczające (a zapewne nie są)
10 Dokumentacja dla użytkownika
Opcjonalnie – dla chętnych
Na podstawie projektu docelowej aplikacji, a nie zaimplementowanego prototypu architektury

4-6 stron z obrazkami (np. zrzuty ekranowe, polecenia do wpisania na konsoli, itp.)
    • pisana językiem odpowiednim do grupy odbiorców – czyli najczęściej nie do informatyków
    • może to być przebieg krok po kroku obsługi jednej głównej funkcji systemu, kilku mniejszych, instrukcja instalacji lub innej pomocniczej czynności.
11 Podsumowanie
11.1 Szczegółowe nakłady projektowe członków zespołu
tabela (kolumny to osoby, wiersze to działania) pokazująca, kto ile czasu poświęcił na projekt oraz procentowy udział każdej osoby w danym zadaniu oraz wiersz podsumowania – procentowy udział każdej osoby w skali całego projektu
12 Inne informacje
przydatne informacje, które nie zostały ujęte we wcześniejszych punktach
