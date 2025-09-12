> :white_check_mark: *Jeśli będziesz mieć problem z rozwiązaniem tego zadania, poproś o pomoc na odpowiednim kanale na Slacku, tj. `s9e05-django-containerization` (dotyczy [mentee](https://devmentor.pl/mentoring/)) lub na ogólnodostępnej i bezpłatnej [społeczności na Discordzie](https://devmentor.pl/discord). Pamiętaj, aby treść Twojego wpisu spełniała [odpowiednie kryteria](https://devmentor.pl/jak-prosic-o-pomoc/).*

&nbsp;

# `#01` Docker konteneryzacja

Twoim zadaniem jest uruchomienie interpretera Pythona **w kontenerze Dockera** na bazie obrazu `python:3.12`, wykonanie kilku prostych operacji w sesji i poprawne zakończenie pracy.
**To zadanie jest całkowicie niezależne** — wykonujesz je w osobnym katalogu/środowisku i **nie** korzystasz z rozwiązań ani plików z innych ćwiczeń.

To ćwiczenie pozwoli Ci przećwiczyć:

* uruchamianie kontenera na bazie oficjalnego obrazu z Docker Hub,
* pracę w trybie interaktywnym (`-it`) i wychodzenie z kontenera,
* sprawdzanie stanu kontenerów (`docker ps`, `docker ps -a`).

## Zakres zadania

1. Uruchom **nowy** kontener na bazie obrazu `python:3.12` w trybie interaktywnym, nadając mu prostą i jasną nazwę: `python-test`.
2. Wewnątrz interpretera Pythona:

   * sprawdź wersję Pythona,
   * wykonaj obliczenie `2 + 2`,
   * zaimportuj moduł `sys` i wyświetl `sys.platform`.
3. Zakończ pracę interpretera tak, aby kontener **się zatrzymał** (nie usuwaj go).
4. Zweryfikuj stan kontenera na hoście:

   * pokaż listę działających kontenerów,
   * pokaż listę **wszystkich** kontenerów (w tym zatrzymanych).

## Wymagania funkcjonalne

### Oczekiwane rezultaty

| Akcja                                         | Oczekiwany rezultat                                          |
| --------------------------------------------- | ------------------------------------------------------------ |
| Uruchomienie kontenera o nazwie `python-test` | Widzisz prompt Pythona `>>>`                                 |
| `print(2 + 2)`                                | Na ekranie: `4`                                              |
| `import sys; print(sys.platform)`             | Wyświetla identyfikator platformy (np. `linux`)              |
| Wyjście z interpretera                        | Powrót do powłoki hosta                                      |
| `docker ps`                                   | Kontener `python-test` **nie** jest widoczny (bo zatrzymany) |
| `docker ps -a`                                | Widać `python-test` ze statusem `Exited (0)`                 |

## Wskazówki

* Uruchom kontener w trybie interaktywnym z TTY: `-it`.
* Nazwę kontenera ustaw przez `--name python-test`.
* Z interpretera wyjdziesz poleceniem `exit()` albo skrótem `Ctrl+D`.
* Do weryfikacji stanu użyj `docker ps` (tylko aktywne) oraz `docker ps -a` (wszystkie).


## Testowanie

* W trakcie sesji wykonaj:
  `import sys; print(sys.version)` — sprawdzisz wersję Pythona działającego **w kontenerze**.
* Po wyjściu z kontenera uruchom:
  `docker ps` oraz `docker ps -a` — upewnisz się, że kontener działał i został poprawnie zatrzymany.


## Twoje rozwiązanie powinno zawierać

* Komendę uruchamiającą kontener z nazwą `python-test`,
* **zrzuty ekranu** pokazujące:

  * działanie interpretera i wyniki poleceń wewnątrz kontenera,
  * wyniki `docker ps` i `docker ps -a` po zakończeniu pracy.



&nbsp;
> :no_entry: *Jeśli nie posiadasz materiałów do tego zadania tj. **PDF, projekt + Code Review**, znajdziesz je na stronie [devmentor.pl](https://devmentor.pl/workshop-django-containerization)*

> :arrow_left: ~~*poprzednie zadanie*~~ | [*następne zadanie*](./../02) :arrow_right:
