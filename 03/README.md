> :white_check_mark: *Jeśli będziesz mieć problem z rozwiązaniem tego zadania, poproś o pomoc na odpowiednim kanale na Slacku, tj. `s9e05-django-containerization` (dotyczy [mentee](https://devmentor.pl/mentoring-javascript/)) lub na ogólnodostępnej i bezpłatnej [społeczności na Discordzie](https://devmentor.pl/discord). Pamiętaj, aby treść Twojego wpisu spełniała [odpowiednie kryteria](https://devmentor.pl/jak-prosic-o-pomoc/).*

&nbsp;

# `#03` Docker konteneryzacja

Twoim zadaniem jest przygotowanie **obrazu Dockera** dla **aplikacji Django** oraz uruchomienie jej w kontenerze.
**To zadanie jest całkowicie niezależne** — wykonujesz je w osobnym katalogu/środowisku i **nie** korzystasz z rozwiązań ani plików z innych ćwiczeń.

To ćwiczenie pozwoli Ci przećwiczyć:

* jak „wprowadzić” Django do obrazu (poprzez zależności instalowane w czasie budowania),
* budowę obrazu z pliku **Dockerfile**,
* uruchomienie serwera developerskiego Django w kontenerze i sprawdzenie działania w przeglądarce.


## Co masz przygotować (artefakty)

1. **Struktura katalogu projektu** zawierająca co najmniej:

   * `requirements.txt` z wpisem zapewniającym instalację Django,
   * kod projektu Django (pliki projektu z `manage.py` oraz folderem z ustawieniami),
   * `Dockerfile` budujący obraz aplikacji.

2. **Obraz Dockera** o czytelnej nazwie: `django-app`.

3. **Kontener** uruchomiony z tego obrazu o czytelnej nazwie: `django-server`, z wystawionym na hoście portem aplikacji.

4. **Zrzuty ekranu** potwierdzające wykonanie pracy:

   * wynik zbudowania obrazu,
   * lista działających kontenerów z widocznym `django-server`,
   * strona aplikacji dostępna pod adresem przeglądarkowym wskazanym poniżej.


## Kroki do wykonania

1. **Przygotuj katalog roboczy** wyłącznie dla tego zadania.
   Ustal, że wewnątrz znajdą się: `requirements.txt`, `Dockerfile` i projekt Django (z `manage.py`).

2. **Zdefiniuj zależności w `requirements.txt`** tak, aby podczas budowy obrazu zainstalowało się **Django** (dozwolony jest zakres wersji; użyj współczesnej stabilnej linii 4.x/5.x zgodnej z Pythonem 3.12).

3. **Zapewnij szkielet projektu Django** w tym katalogu (ma być możliwe uruchomienie serwera deweloperskiego).
   Minimalny stan do uruchomienia:

   * plik `manage.py`,
   * katalog z ustawieniami (np. `app/settings.py`),
   * skonfigurowane `ALLOWED_HOSTS` tak, aby akceptować ruch z hosta (dla ćwiczeń dopuszczalne jest ustawienie umożliwiające dostęp lokalny).

4. **Utwórz `Dockerfile`**, który:

   * korzysta z oficjalnego obrazu Pythona odpowiedniego dla Django (Python 3.12),
   * ustawia **katalog roboczy** wewnątrz obrazu (np. `/app`),
   * **najpierw** kopiuje `requirements.txt` i **instaluje zależności** wewnątrz obrazu,
   * **następnie** kopiuje resztę plików projektu do katalogu roboczego,
   * **udostępnia port aplikacji** używany przez serwer developerski Django,
   * posiada **polecenie startowe**, które uruchamia serwer Django w trybie developerskim, nasłuchujący na wszystkich interfejsach w kontenerze (adres `0.0.0.0` na standardowym porcie aplikacji).

5. **Zbuduj obraz** z bieżącego katalogu i nadaj mu nazwę **`django-app`**.

6. **Uruchom kontener** na podstawie zbudowanego obrazu:

   * nadaj kontenerowi nazwę **`django-server`**,
   * wystaw port tak, aby aplikacja była dostępna lokalnie w przeglądarce (mapowanie portu kontenera na port hosta),
   * utrzymuj czytelne nazewnictwo (nie używaj losowych nazw).

7. **Zweryfikuj działanie**:

   * sprawdź listę kontenerów — `django-server` powinien mieć status „Up”,
   * wejdź w przeglądarce na **`http://localhost:8000`** (jeśli użyjesz innego mapowania portu, odwiedź odpowiedni adres),
   * upewnij się, że widać stronę startową Django albo stronę Twojej aplikacji (jeśli dodałeś widoki).


## Wymagania funkcjonalne (kryteria akceptacji)

| Element                  | Co ma być spełnione                                                                                                                          |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------- |
| `requirements.txt`       | Zawiera wpis instalujący Django (wersja zgodna z Pythonem 3.12).                                                                             |
| Projekt Django           | Da się uruchomić serwer developerski; `ALLOWED_HOSTS` umożliwia dostęp z hosta.                                                              |
| `Dockerfile`             | Instalacja zależności przed kopiowaniem kodu; poprawny katalog roboczy; port udostępniony; polecenie startowe uruchamia serwer na `0.0.0.0`. |
| Obraz `django-app`       | Zostaje zbudowany bez błędów.                                                                                                                |
| Kontener `django-server` | Uruchamia się i działa (status „Up”).                                                                                                        |
| Dostęp w przeglądarce    | Aplikacja dostępna pod adresem wskazanym (domyślnie `http://localhost:8000`).                                                                |

## Wskazówki organizacyjne (bez gotowca)

* **Nazwy:** trzymaj się prostych nazw: obraz `django-app`, kontener `django-server`.
* **Port:** standardowo Django używa portu 8000 w kontenerze; pamiętaj o mapowaniu na hosta.
* **Kolejność w `Dockerfile`:** najpierw instaluj zależności z `requirements.txt`, dopiero potem kopiuj resztę plików — przyspiesza to przebudowy.
* **Adres nasłuchiwania:** serwer developerski musi nasłuchiwać na `0.0.0.0`, inaczej nie wyjdzie poza kontener.
* **Diagnostyka:** w razie problemów przejrzyj logi kontenera; sprawdź też, czy port na hoście nie jest zajęty.

## Co masz oddać

* Katalog zadania zawierający: `requirements.txt`, `Dockerfile`, pliki projektu Django.
* Zrzuty ekranu:

  1. rezultat budowania obrazu,
  2. lista uruchomionych kontenerów z widocznym `django-server`,
  3. widok działającej aplikacji w przeglądarce pod adresem lokalnym.


&nbsp;
> :no_entry: *Jeśli nie posiadasz materiałów do tego zadania tj. **PDF, projekt + Code Review**, znajdziesz je na stronie [devmentor.pl](https://devmentor.pl/workshop-django-containerization)*

> :arrow_left: [*poprzednie zadanie*](./../02) | [*następne zadanie*](./../04) :arrow_right:
