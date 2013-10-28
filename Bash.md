###Laboratorium 1

1\. Używając linii poleceń stwórz strukturę katalogów:
```sh
  mkdir -p dom nauka/{c,logo,pascal} praca/{dokumenty,zlecenia/{niezrealizowane,zrealizowane}}
```

2\. Przejdź do katalogu *dom* i utwórz katalog *wazne-sprawy*:
```sh
  cd dom

  mkdir wazne-sprawy
```
  
3\. Wejdź do katalogu *wazne-sprawy* i utwórz tam pusty plik *rachunki.txt*:
```sh
  cd wazne-sprawy

  touch rachunki.txt
```

4\. Będąc w katalogu *wazne-sprawy* skopiuj plik *rachunki.txt* do katalogu zrealizowane:
```sh
  cp ./rachunki.txt ~/temp/praca/zlecenia/zrealizowane
```

5\. Przejdź do katalogu zrealizowane i zmień nazwę pliku *rachunki.txt* na *wykonano.txt*:
```sh
  mv rachunki.txt wykonano.txt
```

6\. Utwórz plik *wykonano.txt* wielkości 11 bajtów, następnie podziel go na pliki wielkości 5 bajtów. W ten sposób otrzymasz 3 pliki. (split):
```sh
  cat > wykonano.txt
  0123456789
  
  split -b 5 wykonano.txt
```
  
7\. Będąc w katalogu *logo* skopiuj powyżej otrzymane 3 pliki do katalogu dokumenty:
```sh
  cp ~/temp/praca/zlecenia/zrealizowane/{xaa,xab,xac} ~/temp/praca/dokumenty
```

8\. Będąc w katalogu *dokumenty* połącz skopiowane 3 pliki w plik *odtworzono.txt*, tak aby otrzymać plik o zawartości identycznej z wykonano.txt: 
Następnie plik *odtworzono.txt* skopiuj do katalogu *wazne-sprawy*.
```sh
  cat xaa xab xac > odtworzono.txt
  
  cp odtworzono.txt ~/temp/dom/wazne-sprawy
```

9\. Będąc w katalogu *wazne-sprawy* sprawdź, czy są jakieś różnice w zawartości plików *wykonano.txt* i *odtworzono.txt*:
```sh
  diff -q odtworzono.txt ~/temp/praca/zlecenia/zrealizowane/wykonano.txt 
```

10\. 
-Wyświetl kalendarz na październik 2009 r. (cal):
```sh
  cal 10 2009
```

-Wyświetl kalendarz na wrzesień, październik i listopad 2009 r. z miesiącami obok siebie (cal):  
```sh
  cal -3 10 2009
```

-Wyświetl kalendarz na październik, listopad i grudzień 2009 r. w taki sposób:
```sh
  cal -3 11 2009
```

-I jeszcze raz na wrzesień i październik oraz na październik i listopad 2009 r z miesiącami obok siebie (cal, cut?):
```sh
  cal -3 10 2009 | cut -c 1-43
  cal -3 11 2009 | cut -c 1-43
```

11\. Jaki był dzień tygodnia 25 maja 1975 r. (cal i date)
```sh
  date +%A -d '1975-05-25'
```

###Laboratorium 2

1\. Wyświetl na ekran 2 pierwsze wiersze pliku *program.c*. (head)
```sh
head -2l program.c
```

2\. Wyświetl na ekran 4 ostatnie wiersze pliku *program.c*. (head, tail)
```sh
tail -4l program.c
```

3\. W pliku *program.c* znajdź wszystkie wiersze z wystąpieniem słowa *„main”*. (grep)
```sh
grep main program.c
```

4\. Plikowi *program.c* nadaj następujące uprawnienia: właściciel – czytanie, pisanie, grupa – czytanie, pozostali użytkownicy: brak uprawnień. (chmod)
```sh
chmod 640 program.c
```

5\. Będąc w katalogu *temp* przenieś katalog *wazne-sprawy* do katalogu *praca*.
```sh
mv dom/waznesprawy praca
```

6\. Zarchiwizuj cały katalog *temp*. (zip i tar)
```sh
tar -cf temp.tar temp
```

7\. Usuń katalog *temp*.
```sh
rm -rf temp
```

8\. Odtwórz z archiwum katalog *temp*. (unzip i tar)
```sh
tar -xf temp.tar
```

9\. Posprzątaj na swoim koncie.
```sh
rm -rf temp.tar
```

10\. Wyświetl linijki ze środka pliku *program.c*, licząc od góry (przykład: linijki 8,9,10)
```sh
head program.c | tail -3
```

11\. Wyświetl linijki ze środka tego pliku, licząc od dołu (przykład: linijki 3,4,5)
```sh
tail -5 program.c | head -3
```
lub (ten sam wynik, ale metodą z zadania 10)
```sh
tac program.c | head -5 | tail -3 | tac
```
