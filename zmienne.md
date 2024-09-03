# Zmienne 
---
### Zmienne liczbowe
 - `short a;` całkowite do 32k
 - `int a;` całkowite do 2 mld
 - `long long a;` całkowite mega duże
 - `unsigned short a;` tylko dodatnie całkowite, ale 2 razy większy zakres
 - `float a;` rzeczywiste, do 6 cyfr po przecinku
 - `double a;` rzeczywiste do 15 cyfr po przecinku
### Zmienne tekstowe
 - `char a = 'b';` pojedyńcze znaki
 - `string tekst = "Ala ma kota";` tekst (tablica znaków)<br>
 warto zwrócić uwagę na to, że znaki i tekst mają inne cudzysłowy
### Działania na stringu
 - `tekst.size()` ilość znaków w stringu
 - `tekst.substr(2);` kopiuje tekst od 2 pozycji do końca
 - `tekst.substr(2,4);` kopiuje tekst od 2 do 4 pozycji
 - `tekst.find("ala");` zwraca numer pozycji na której znajduje się szukany tekst 
 - `tekst.find("ala",3);` zwraca numer pozycji na której znajduje się szukany tekst, zaczynając od 3 pozycji
 - `tekst.rfind("a",6);` zwraca numer pozycji, ale szuka od tyłu, w tym przypadku idzie 6->0
<br>**UWAGA!** find zawsze zwróci jakiś wynik, ale jeśli nie ma tego znaku w stringu to będzie to liczba większa niż rozmiar stringa
### Tablice
 - `int tablica[4]={1,2,3,4};` Tablica statyczna, nie można zmieniać rozmiaru
 - `vector<int>V(12,0);` Tablica dynamiczna *V* o długości 12, wypełniona 0 (zarowno dlugosc jak i wypelnienie jest opcjonalne)
 - `tablica[2]` odwołuje się do **3** komórki (numerowanie od 0)
### Działania na vektorach
 załóżmy, że mamy zmienną V typu vektor<int>

 - `V.size();` zwraca ilość komórek
 - `V.push_back(2);` dodaje na koniec vektora komórkę o wartości *2*
 - `V.pop_back();` usuwa ostatnią komórkę
 - `V.clear();` usuwa wszystkie komórki
 - `V.empty();` zwraca *true* jeśli tablica jest pusta
 - `V.insert(V.begin() + 2, 9);` wstawia komórkę o zawartości *9* na 2 pozycję w tablicy
 - `V.erase(V.begin() + 8);` usuwa komórkę na 8 pozycji
 - `V.erase(V.begin()+2, V.begin()+5);` usuwa komórki od 2 do 5 włącznie 
### Tablice wielowymiarowe
tworzymy poprostu vektor wypełniony vektorami
```cpp 
vector< vector<int> > V (wiersze, vector<int>(kolumny));
```
odwołanie wtedy wygląda tak `V[2][5]`
### Mapy
mapy są potężnym narzędziem pozwalającym na tworzenie tablic, których indexem nie musi być int, lub tworzenie komórek o indexie np *5* bez istnienia komórek 0-4

 - `map<int,int>M;` tworzymy mapę *M* o indexach typu *int* i wartościach typu *int*
 - `map<int,int>::iterator it;` tworzymy iterator *it*, który pozwoli na przemieszczanie się po kolejnych komórkach
 - `M.size();`
 - `M.empty();`
 - `M.clear();`
 - `M[-1]=18;` wpisywanie wartości (zwróć uwagę, że index może być tu ujemny)
 - `M[124]++;` zwiększamy wartość wcześniej nie używanej komórki o 1, więc teraz jest *1* (domyślnie miała *0*)
 - `M.count(21);` sprawdzamy czy komórka istnieje
###Iterator
Iterator to wskaźnik, za pomocą którego jesteśmy w stanie iść element po elemencie przez zmienne wielowymiarowe. W przypadku typu zmiennych takich jak **Mapy**, gdzie kolejne komórki nie są numerowane po kolei jest on niezbędny.
```cpp
map<int,int>::iterator it;
for(it=M.begin();it!=M.end();it++)
        cout<<it->first<<"\t:\t"<<M[it->first]<<"\t:\t"<<it->second<<endl;
```
 - `it->first` to jest numer komórki
 - `it->second` to wartość komórki, czyli to samo co `M[it->first]`
<br> warto zwrócić uwagę na warunki pętli. iterator idzie od poczatku `M.begin()`, a konczy gdy dochodzi do końca `M.end()`
###Reverse iterator
Tak, istnieje coś takiego jak *reverse iterator*. Jest to iterator, tyle że idzie od tyłu (obv)
```cpp
map<int,int>::reverse_iterator rit;
for(rit=M.rbegin();rit!=M.rend();rit++)
        cout<<rit->first<<"\t:\t"<<rit->second<<endl;
```
Ważne do zauważenia jest to, że zamiast `M.begin()` używamy `M.rbegin()`, czyli reverse begin, a nie end! To są wskaźniki i nie można ich tak łatwo poprostu podmienić! Analogicznie z `M.rend()`

### Kolejki i stosy
Kolejka i stos charakteryzują się tym, że nie mamy dostępu do wszystkich elementów w jednym momencie, lecz "wzamian" mogą one zmieniać swoją długość bardzo szybko w przeciwieństwie do np *Vektora*. Dodatkowo kolejka priorytetowa ma jedno z najszybszych możliwych sortowań w c++.

|   	                |Kolejka                        |Kolejka priorytetowa           |Stos                   |
|---	                |:---:	                        |:---:	                        |:---:                  |
|Rodzaj                 |FIFO  	                        |FIFO (z sortowaniem rosnącym)  |FILO                   |
|Definiowanie           |`queue<int>K;` 	        |`priority_queue<int>KP;`       |`stack<int>S;`         |
|Dokładanie elementu    |`K.push(x)`                    |`KP.push(x)`   	        |`S.push(x)`            |
|Zdejmowanie elementu   |`K.pop()`                      |`KP.pop()`                     |`S.pop()`              |
|Odczytywanie elementu  |`K.front()` lub `K.back()`     |`KP.top()` lub `KP.bottom()`   |`S.top()`              |
|Rozmiar                |`K.size()`                     |`KP.size()`                    |`S.size()`             |


 - FIFO = First in First Out
 - FILO = First in Last Out