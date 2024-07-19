# Obsługa plików
---
```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
int liczba;
string sliczba;
fstream plik,plik1;//zmienna dla plikow; bilblioteka fstream
plik.open("dane.txt",ios::in);//"D:\dane\dane.txt" dla pliku w innym folderze.  in-do odczytu | out- do zapisu
if(plik.is_open()){//ewentualnie if(plik.good());
    cout<<"Plik otwarto \n";//wazne by na wszelki sprawdzi

    while(!plik.eof()&&plik>>liczba){ //eof = end of file
       // plik>>liczba moze tez stringa wczytsac
       //plik>>liczba uznaje spacje i entery jako nic i koniec wczytywania (tak samo jak cin);
        cout<<liczba<<" ";

    }
}
/* zamiast plik>>liczba (odpowiednik cina) mozna wczytac getline(plik,sliczba); on wtedy pobierze cala linijke do stringa (jak normalnie getline);

while(!plik.eof()){
    getline(plik,sliczba);
    if(sliczba!="") //by pominac puste wiersze;
        cout<<sliczba;
}
*/
else
    cout<<"Blad pliku";
plik.close();//zamyka plik

plik1.open("danewyjsciowe.txt",ios::out);//jeli ten plik nie istnieje to go utworzy, a jesli istnieje to zostanie wykasowany
plik1<<"To jest test zapisu"<<endl<<"1234"<<endl<<5678;//wpisywanie do pliku ios:out

plik1.close();
return 0;
}
//czyli plik>> to jest cin, a getline(plik,liczba); to getline

```