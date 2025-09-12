> :white_check_mark: *Jeśli będziesz mieć problem z rozwiązaniem tego zadania, poproś o pomoc na odpowiednim kanale na Slacku, tj. `s9e05-django-containerization` (dotyczy [mentee](https://devmentor.pl/mentoring-javascript/)) lub na ogólnodostępnej i bezpłatnej [społeczności na Discordzie](https://devmentor.pl/discord). Pamiętaj, aby treść Twojego wpisu spełniała [odpowiednie kryteria](https://devmentor.pl/jak-prosic-o-pomoc/).*

&nbsp;

# `#05` Docker konteneryzacja

Twoim zadaniem jest przygotowanie projektu **Django uruchamianego w Dockerze** tak, aby można go było **łatwo odtworzyć na innym komputerze** bez dodatkowych instrukcji ustnych.
**To zadanie jest całkowicie niezależne** — wykonujesz je w osobnym katalogu/środowisku i **nie** korzystasz z rozwiązań ani plików z innych ćwiczeń.

To ćwiczenie pozwoli Ci przećwiczyć:

* kompletowanie minimalnego zestawu plików do uruchomienia projektu przez inną osobę,
* przygotowanie jednoznacznych poleceń i konfiguracji (Dockerfile, docker-compose, `.env`, README),
* weryfikację odtwarzalności na czystym środowisku.

## Zakres zadania

1. **Struktura repozytorium (katalogu zadania)**
   Przygotuj katalog zawierający co najmniej:

   * `README.md` z instrukcją uruchomienia krok po kroku (bez skrótów myślowych),
   * `requirements.txt` (zależności Pythona wymagane przez aplikację),
   * `Dockerfile` dla aplikacji Django,
   * opcjonalny `docker-compose.yml` (jeśli używasz dodatkowych usług, np. bazy),
   * opcjonalny plik `.env.example` (szablon zmiennych środowiskowych, **bez haseł**),
   * kod projektu Django z `manage.py` i folderem z ustawieniami.

2. **Instrukcja uruchomienia w `README.md`**
   Instrukcja ma umożliwiać **osobie trzeciej** (na czystej maszynie z Dockerem) uruchomienie aplikacji bez dopowiedzeń. Uwzględnij:

   * wymagania wstępne (posiadanie Dockera, ewentualnie Docker Compose),
   * komendę budowania obrazu,
   * komendę uruchomienia kontenera (lub `docker compose up`),
   * adres URL w przeglądarce (np. `http://localhost:8000`),
   * sposób zatrzymania aplikacji,
   * informację o używanym porcie i co zrobić, gdy jest zajęty,
   * jeśli używasz Compose: kolejność/kroki migracji bazy (wywołanie komend w kontenerze).

3. **Konfiguracja aplikacji**

   * Serwer developerski Django ma nasłuchiwać na `0.0.0.0` wewnątrz kontenera.
   * `ALLOWED_HOSTS` skonfiguruj tak, by dostęp z hosta był możliwy w środowisku lokalnym.
   * Jeśli projekt wymaga zmiennych środowiskowych, **udokumentuj je** w `.env.example` i w `README.md` (nazwa, rola, przykładowa wartość).

4. **Uruchomienie i weryfikacja lokalna**

   * Zbuduj obraz i uruchom kontener(y) zgodnie z instrukcją z `README.md`.
   * Sprawdź, że projekt startuje i strona jest dostępna pod wskazanym adresem.

5. **Pakowanie i „odtworzenie na czysto”**

   * Przygotuj archiwum `.zip` lub `.tar.gz` katalogu zadania (bez zbędnych plików tymczasowych).
   * Zweryfikuj, że po rozpakowaniu na innym katalogu/koncie użytkownika (albo innej maszynie) i wykonaniu kroków z `README.md` aplikacja uruchamia się poprawnie.


## Wymagania funkcjonalne (kryteria akceptacji)

| Element                   | Co ma być spełnione                                                                                         |
| ------------------------- | ----------------------------------------------------------------------------------------------------------- |
| Kompletny katalog zadania | Zawiera: `README.md`, `requirements.txt`, `Dockerfile`, kod projektu; opcjonalnie Compose i `.env.example`. |
| Instrukcja w `README.md`  | Jednoznaczna, kompletna, z komendami do skopiowania; obejmuje budowę, uruchomienie, dostęp, stop.           |
| Konfiguracja serwera      | Django nasłuchuje na `0.0.0.0`; port wystawiony na hosta; `ALLOWED_HOSTS` umożliwia dostęp lokalny.         |
| Zależności                | Instalowane podczas budowy obrazu z `requirements.txt`.                                                     |
| Odtwarzalność             | Po rozpakowaniu archiwum i wykonaniu instrukcji projekt działa bez dodatkowych kroków.                      |


## Wskazówki (organizacyjne, bez gotowca)

* **Nazwy:** trzymaj się prostych i spójnych nazw obrazu/kontenera/usług.
* **Powtarzalność:** w `Dockerfile` najpierw instaluj zależności z `requirements.txt`, potem kopiuj resztę kodu.
* **Porty:** wskaż w `README.md`, które porty są używane i jak je zmienić w razie konfliktu.
* **Zmienne środowiskowe:** nie commituj wrażliwych danych; pokaż wzór w `.env.example`.
* **Migracje (jeśli dotyczą):** opisz, **kiedy i jak** wykonać (jedna, krótka komenda do skopiowania).
* **Diagnostyka:** dodaj sekcję „Najczęstsze problemy” (np. konflikt portu, brak uprawnień do gniazd, błędy zależności).


## Testowanie

Przygotuj **zrzuty ekranu** potwierdzające:

1. pomyślne zbudowanie obrazu,
2. działające kontenery (lista po uruchomieniu),
3. stronę aplikacji w przeglądarce pod wskazanym adresem,
4. wynik powtórnego uruchomienia z rozpakowanego archiwum (dowód odtwarzalności).

## Co masz oddać

* Spakowany katalog projektu (`.zip` / `.tar.gz`) z zawartością opisaną w „Zakres zadania”.
* **Zrzuty ekranu**: budowanie, uruchomione kontenery, strona w przeglądarce, udany „clean run” z archiwum.


&nbsp;
> :no_entry: *Jeśli nie posiadasz materiałów do tego zadania tj. **PDF, projekt + Code Review**, znajdziesz je na stronie [devmentor.pl](https://devmentor.pl/workshop-django-containerization)*

> :arrow_left: [*poprzednie zadanie*](./../04) | ~~*następne zadanie*~~ :arrow_right:
