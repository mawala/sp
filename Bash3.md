###Laboratorium 3

1\. Wyświetl plik */etc/passwd* z podziałem na strony przyjmując, że strona na 5 linii tekstu. (raczej more niż less)
```sh
more -5 /etc/passwd
```
2\. Korzystając z polecenia *cat* utwórz plik *tekst3.txt*, który będzie składał się z zawartości pliku *tekst1.txt*, 
ciągu znaków podanego ze standardowego wejścia (klawiatury) i pliku *tekst2.txt*.
```sh
cat tekst1.txt - tekst2.txt > tekst3.txt 
```
3\. Wyświetl po 5 pierwszych linii wszystkich plików w swoim katalogu domowym 
w taki sposób, aby nie były wyświetlane ich nazwy.
```sh
