###Laboratorium 3

1\. Wyświetl plik */etc/passwd* z podziałem na strony przyjmując, że strona na 5 linii tekstu (raczej more niż less)
```sh
more -5 /etc/passwd
```
2\. Korzystając z polecenia *cat* utwórz plik *tekst3.txt*, który będzie składał się z zawartości pliku *tekst1.txt*, 
ciągu znaków podanego ze standardowego wejścia (klawiatury) i pliku *tekst2.txt*
```sh
cat tekst1.txt - tekst2.txt > tekst3.txt 
```
3\. Wyświetl po 5 pierwszych linii wszystkich plików w swoim katalogu domowym 
w taki sposób, aby nie były wyświetlane ich nazwy
```sh
head -qn 5 *
```
4\. Wyświetl linie o numerach 3, 4 i 5 z pliku */etc/passwd*
```sh
head -n 5 /etc/passwd | tail -n 3
```
5\. Wyświetl linie o numerach 7, 6 i 5 od końca pliku */etc/passwd*
```sh
tail -n 7 /etc/passwd | head -n 3
```
6\. Wyświetl zawartość pliku */etc/passwd* w jednej linii
```sh
cat /etc/passwd | tr -d "\n"
```
*lub*
```sh
x=$(cat /etc/passwd) echo $x
```
7\. Za pomocą filtru *tr* wykonaj modyfikację pliku *plik.txt*, polegającą na umieszczeniu każdego słowa w osobnej linii
```sh
cat plik.txt | tr " " "\n"
```
8\.  Zlicz wszystkie pliki znajdujące się w katalogu */etc* i jego podkatalogach
```sh
find /etc -type f 2>&1 | wc -l
```
9\. Napisać polecenie zliczające ilość znaków z pierwszych trzech linii pliku */etc/passwd*
```sh
head -n 3 /etc/passwd | wc -c
```
