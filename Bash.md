###Laboratorium 1

1\. Używając linii poleceń stwórz strukturę katalogów:

  mkdir -p dom nauka/{c,logo,pascal} praca/{dokumenty,zlecenia/{niezrealizowane,zrealizowane}}


2\. Przejdź do katalogu dom i utwórz katalog wazne-sprawy:

  cd dom

  mkdir wazne-sprawy
  
  
3\. Wejdź do katalogu wazne-sprawy i utwórz tam pusty plik rachunki.txt:

  cd wazne-sprawy

  touch rachunki.txt


4\. Będąc w katalogu wazne-sprawy skopiuj plik rachunki.txt do katalogu zrealizowane:

  cp ./rachunki.txt ~/temp/praca/zlecenia/zrealizowane


5\. Przejdź do katalogu zrealizowane i zmień nazwę pliku rachunki.txt na wykonano.txt:

  mv rachunki.txt wykonano.txt


6\. Utwórz plik wykonano.txt wielkości 11 bajtów, następnie podziel go na pliki wielkości 5 bajtów. W ten sposób otrzymasz 3 pliki. (split):

  cat > wykonano.txt
  0123456789
  
  split -b 5 wykonano.txt

  
7\. Będąc w katalogu logo skopiuj powyżej otrzymane 3 pliki do katalogu dokumenty:

  cp ~/temp/praca/zlecenia/zrealizowane/{xaa,xab,xac} ~/temp/praca/dokumenty


8\. Będąc w katalogu dokumenty połącz skopiowane 3 pliki w plik odtworzono.txt, tak aby otrzymać plik o zawartości identycznej z wykonano.txt: 
Następnie plik odtworzono.txt skopiuj do katalogu wazne-sprawy.

  cat xaa xab xac > odtworzono.txt
  
  cp odtworzono.txt ~/temp/dom/wazne-sprawy

9\. Będąc w katalogu wazne-sprawy sprawdź, czy są jakieś różnice w zawartości plików wykonano.txt i odtworzono.txt:

  diff -q odtworzono.txt ~/temp/praca/zlecenia/zrealizowane/wykonano.txt 


10\. 
-Wyświetl kalendarz na październik 2009 r. (cal):

  cal 10 2009
  
-Wyświetl kalendarz na wrzesień, październik i listopad 2009 r. z miesiącami obok siebie (cal):  

  cal -3 10 2009
  
-Wyświetl kalendarz na październik, listopad i grudzień 2009 r. w taki sposób:

  cal -3 11 2009
  
-I jeszcze raz na wrzesień i październik oraz na październik i listopad 2009 r z miesiącami obok siebie (cal, cut?):

11\. Jaki był dzień tygodnia 25 maja 1975 r. (cal i date)
