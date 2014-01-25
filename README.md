Srodowisko-Programisty
======================
Zadanie 1

Wyświetl listę plików z aktualnego katalogu, zamieniając wszystkie małe litery na duże.

$ ls | tr [:lower:] [:upper:]
2009-06-12-JEKYLL-HOWTO.MARKDOWN
2009-10-17-ODPOWIEDZI-DO-ZADAN-LABORATORIUM-1.MARKDOWN
2009-10-19-ABOUT.MARKDOWN
2009-10-25-ODPOWIEDZI2.MARKDOWN
2009-10-25-ODPOWIEDZI3.MARKDOWN
2009-10-26-ODPOWIEDZI4.MARKDOWN
$ 
Zadanie 2

Wyświetl listę praw dostępu do plików w aktualnym katalogu, ich rozmiar i nazwę.

$ find . -printf "Plik: %f Rozmiar: %s Prawa: %M \n" -maxdepth 1
Zadanie 3

Wyświetl listę plików w aktualnym katalogu, posortowaną według rozmiaru pliku.

$ ls --sort=size -1
Zadanie 4

Wyświetl zawartość pliku /etc/passwd posortowaną według numerów UID w kolejności od największego do najmniejszego.

cat /etc/passwd | sort --reverse --field-separator=":" --general-numeric-sort --key 3
Zadanie 5

Wyświetl zawartość pliku /etc/passwd posortowaną najpierw według numerów GID w kolejności od największego do najmniejszego, a następnie UID.

cat /etc/passwd | sort --field-separator=":" --general-numeric-sort --key 4,3 --reverse
Zadanie 6

Podaj liczbę plików każdego użytkownika.

$ find / -printf "%u\n" 2> /dev/null | sort | uniq -c
Zadanie 7

Sporządź statystykę praw dostępu (dla każdego z praw dostępu podaj ile razy zostało ono przydzielone).

$ find -printf "%m\n" | sort | uniq -c
