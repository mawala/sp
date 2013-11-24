### Laboratorium 4

1\. Wyświetl listę plików z aktualnego katalogu, zamieniając wszystkie małe litery na duże
```sh
ls -1 --classify | sed -e '/[/]/d' | tr 'a-z' 'A-Z'
```
2\. Wyświetl listę praw dostępu do plików w aktualnym katalogu, ich rozmiar i nazwę
```sh
ls -g --no-group --human-readable --classify --full-time | tr -s " " | \
 cut -f 1,3,7 -d " " | sed -e '/^d/d' | tr " " "\t"
```
3\. Wyświetl listę plików w aktualnym katalogu, posortowaną według rozmiaru pliku
```sh
ls -lS1 --human-readable | sed -e '/^d/d' | tr -s " " | cut -f 5,9 -d " " | tac 
```
4\. Wyświetl zawartość pliku */etc/passwd* posortowaną według numerów UID w kolejności 
od największego do najmniejszego
```sh
cat /etc/passwd | sort -t ":" -k 3 -nr
```
5\. Wyświetl zawartość pliku */etc/passwd* posortowaną najpierw według numerów GID 
w kolejności od największego do najmniejszego, a następnie UID
```sh
cat /etc/passwd | sort -t ":" -k 4 -nr -k 3 -nr
```
6\. Podaj liczbę plików każdego użytkownika
```sh
find -type f -printf "%U\n" | sort | uniq -c | sort
```
7\. Sporządź statystykę praw dostępu (dla każdego z praw dostępu podaj, ile razy zostało 
ono przydzielone)
```sh
find -type f -printf "%m\n" | sort | uniq -c
```
