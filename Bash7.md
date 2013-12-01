###Laboratorium 7

1\. W bieżącym katalogu zamienić rozszerzenia wszystkich plików z rozszerzeniem *htm* na *html*\. 
Jeżeli w nazwie pliku istnieje spacja, to należy zamienić ją na znak podkreślenia
```sh
#!/bin/bash

FOUND=0

for filename in *
do
  echo "$filename" | grep -q ".htm$"
  if [ $? -eq $FOUND ]
  then
    fname=$filename
    n=$(echo $fname | sed -e "s/.htm/.html/g")
    mv "$fname" "$n"
  fi
done

for filename in *
do
  echo "$filename" | grep -q " "
  if [ $? -eq $FOUND ]
  then
    fname=$filename
    n=$(echo $fname | sed -e "s/ /_/g")
    mv "$fname" "$n"
  fi
done

exit 0
```
2\. Napisać skrypt zawierający funkcję obliczającą silnię. Następnie należy obliczyć silnię z liczby, która jest
argumentem skryptu\. W przypadku niepoprawnego argumentu należy wypisać odpowiedni komunikat\.
```sh
#!/bin/bash
for arg in $1
do
  wynik=1
  licznik=1
  if [ $arg -ge 0 ]
  then
    while [ $licznik -le $arg ]
    do
      wynik=$[ $wynik * $licznik ]
      licznik=$[ $licznik + 1 ]
    done
    echo "Silnia dla $1 = $wynik"
  else
    echo "$1 nie jest poprawnym argumentem"
  fi
done
exit 0
```
