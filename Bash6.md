###Laboratorium 6

1\. W pliku *plik.txt* znajdź wiersze zawierające co najmniej jeden znak
```sh
grep --line-number . plik.txt
```
2\. Znajdź w plikach *pl** wiersze rozpoczynające się od cyfry
```sh
grep --line-number . --regexp=^[0-9] pl*
```
3\. Znajdź pliki, zawierające wiersz, w którym na 9 pozycji występuje litera *r*
```sh
grep --extended-regexp --recursive '^.{8}r.*' *
```
4\. Policz, ilu użytkowników systemu używa powłoki bash (zgodnie z zapisami w pliku */etc/passwd*)
```sh
grep -c bash /etc/passwd
```
5\. Znajdź wiersze zawierające liczby rzymskie w pliku *plik.txt*
```sh
grep --line-number [IVXLCDM] plik.txt
```
