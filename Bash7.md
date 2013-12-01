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
  if [ $? -eg $FOUND ]
  then
    fname=$filename
    n=$(echo $fname | sed -e "s/ /_/g")
    mv "$fname" "$n"
  fi
done

exit 0
```
2\. Napisać skrypt zawierający funkcję obliczającą silnię. Następnie należy obliczyć silnię z liczby, która jest argumentem skryptu\. W przypadku niepoprawnego argumentu należy wypisać odpowiedni komunikat\.
