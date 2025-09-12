> :white_check_mark: *Jeśli będziesz mieć problem z rozwiązaniem tego zadania, poproś o pomoc na odpowiednim kanale na Slacku, tj. `s9e05-django-containerization` (dotyczy [mentee](https://devmentor.pl/mentoring-javascript/)) lub na ogólnodostępnej i bezpłatnej [społeczności na Discordzie](https://devmentor.pl/discord). Pamiętaj, aby treść Twojego wpisu spełniała [odpowiednie kryteria](https://devmentor.pl/jak-prosic-o-pomoc/).*

&nbsp;

# `#02` Docker konteneryzacja

Twoim zadaniem jest uruchomienie serwera WWW **Nginx** w kontenerze Dockera w trybie działającym w tle (detached mode).
**To zadanie jest całkowicie niezależne** — wykonujesz je w osobnym katalogu/środowisku i **nie** korzystasz z rozwiązań ani plików z innych ćwiczeń.

To ćwiczenie pozwoli Ci przećwiczyć:

* uruchamianie usług w tle (`-d`),
* nadawanie czytelnej nazwy kontenerowi,
* zatrzymywanie i ponowne uruchamianie kontenera,
* podstawową inspekcję działania kontenerów.


## Zakres zadania

1. Uruchom kontener na bazie obrazu `nginx`, w trybie **detached** (`-d`), nadając mu prostą i jasną nazwę: `nginx-server`.
2. Zweryfikuj, że kontener działa poprawnie przy pomocy `docker ps`.
3. Otwórz w przeglądarce adres:
   **[http://localhost:80](http://localhost:80)**
   i sprawdź, czy pojawia się domyślna strona Nginx.
4. Zatrzymaj kontener i upewnij się, że nie jest widoczny na liście `docker ps`.
5. Ponownie uruchom zatrzymany kontener i sprawdź, czy serwer znów działa.


## Wymagania funkcjonalne

### Oczekiwane rezultaty

| Akcja                            | Oczekiwany rezultat                                  |
| -------------------------------- | ---------------------------------------------------- |
| Uruchomienie kontenera           | Kontener `nginx-server` działa w tle                 |
| `docker ps`                      | Widoczny `nginx-server` ze statusem `Up`             |
| Wejście na `http://localhost:80` | Strona powitalna Nginx                               |
| Zatrzymanie kontenera            | `docker ps` nie pokazuje `nginx-server`              |
| Ponowne uruchomienie             | `docker ps` pokazuje `nginx-server` ze statusem `Up` |


## Wskazówki

* Użyj opcji **`--name nginx-server`**, aby uniknąć losowej nazwy.
* Do zatrzymania i uruchomienia ponownie możesz użyć:
  `docker stop nginx-server` oraz `docker start nginx-server`.
* Jeśli port 80 jest zajęty, użyj mapowania portów, np.:
  `-p 8080:80` i sprawdź stronę pod adresem **[http://localhost:8080](http://localhost:8080)**.

## Testowanie

* Zrób **zrzut ekranu** z listy kontenerów (`docker ps`) po uruchomieniu Nginx.
* Zrób **zrzut ekranu** z przeglądarki, pokazujący stronę startową Nginx.
* Zrób **zrzut ekranu** z `docker ps` po zatrzymaniu i ponownym uruchomieniu kontenera.

## Twoje rozwiązanie powinno zawierać

* Komendę uruchamiającą kontener z nazwą `nginx-server`,
* **zrzuty ekranu** pokazujące:

  * działający kontener (`docker ps`),
  * stronę powitalną Nginx w przeglądarce,
  * zatrzymany i ponownie uruchomiony kontener.


&nbsp;
> :no_entry: *Jeśli nie posiadasz materiałów do tego zadania tj. **PDF, projekt + Code Review**, znajdziesz je na stronie [devmentor.pl](https://devmentor.pl/workshop-django-containerization)*

> :arrow_left: [*poprzednie zadanie*](./../01) | [*następne zadanie*](./../03) :arrow_right:
