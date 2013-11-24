###Laboratorium 5

1\.  Znajdź w swoim katalogu domowym (bez podkatalogów) wszystkie pliki, które zostały zmodyfikowane 
w ciągu ostatnich dziesięciu dni i wyświetl ich nazwy
```sh
find ~/ -maxdepth 1 -type f -mtime -10 -print
```
2\. Znajdź wszystkie pliki zwykłe w systemie, które mają w nazwie ciąg znaków „conf” i wyświetl ich nazwy na ekranie
```sh
find / -type f -name *conf* 2> /dev/null -print
```
3\. Znajdź w swoim katalogu domowym wszystkie pliki, które nie były używane w ciągu ostatnich 20 dni
```sh
find ~/ -type f -atime +20
```
4\. Znajdź w katalogu */etc* wszystkie **niepuste** podkatalogi i pliki o nazwach zaczynających się na literę „a”
```sh
find /etc \( -type d -and ! -empty -or -type f \) -and -name a* 2> /dev/null
```

5\. Z bieżącego katalogu usuń pliki, których nazwa zaczyna się na literę „x” i zawiera dokładnie trzy znaki
```sh
rm x???
```
6\. Skonstruuj polecenie tworzące katalog, którego nazwą będzie aktualna (w momencie wywołania) 
systemowa data w formacie **rrrr-mm-dd**
```sh
mkdir `date +%Y-%m-%d`
```
