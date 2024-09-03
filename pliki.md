# Obsługa plików
---
Do obsługi plików używamy biblioteki `fstream`, która również znajduje się w `<bits/stdc++.h>`<br>
### Odczyt danych
```cpp
fstream plik;
int liczba;
plik.open("dane.txt",ios::in);
if(plik.good()){
    while(!plik.eof()&&plik>>liczba){
        cout<<liczba<<endl;
    }
}
else
    cout<<"ERROR PLIKU";
plik.close();
```

 - `fstream plik` tworzy zmienną potrzebną do obsługi plików
 - `plik.open("dane.txt",ios::in);` otwiera plik *dane.txt* do odczytu (żeby zapisywać należy `ios::in` zamienić na `ios::out`)
 - `if(plik.good())` sprawdza, czy plik został poprawnie otworzony
 - `plik.eof()` zwróci **prawdę**, gdy dotrzemy do końca pliku
 - `plik>>liczba` wczytuje zawartość pliku do zmiennej *liczba*. Działa to tak samo jak `cin>>` a zatem czyta to aż do białego znaku. Ta linijka umieszczona w warunku sprawdza, czy cokolwiek zostało odczytane.
 - `plik.close();` zamyka plik. jest to BARDZO ważne


### Zapis danych
Zapisujemy analogicznie do `cin>>`
```cpp
fstream plik1;
plik1.open("danewyjsciowe.txt",ios::out);
plik1<<"To jest test zapisu"<<endl<<"1234"<<endl<<5678;
plik1.close();
```
Jeśli wcześniej istniał plik o takiej nazwie to zostanie on usunięty i nadpisany
### Getline
Jeśli chcemy odczytać całą linię z pliku tekstowego do zmiennej używamy polecenia `getline` analogicznie do kożystania z niego z `cin`
```cpp
fstream plik;
string sliczba;
plik.open("test.txt", ios::in);
if(plik.good()){
    while(!plik.eof()){
        getline(plik,sliczba);
        if(sliczba!="")
            cout<<sliczba;
    }
}
else
    cout<<"Blad pliku";
```