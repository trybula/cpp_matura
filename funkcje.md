# Funkcje
---
W c++ mamy 2 rodzaje funkcji:

 - takie, które zwracają wynik (i same w sobie zwykle nic nie wyświetlają)
 - takie, które nie zwracają wyniku

### Funkcje void

to takie, które nie zwracają wyniku
```cpp
void funkcja(){


}
```
### Funkcje int

zwracają wynik. *int* można zamienić innym typem danych, to poprostu oznacza typ w jakim zwrócimy dane
```cpp
int funkcja(){
    return 12;
}

```


### Operowanie funkcjami

możemy je wywołać poprzez `funkcja();`<br>
Do funkcji można również podawać argumenty
```cpp
void funckja(int a, int b){
    cout<<a<<"\t"<<b<<endl;
}
funckcja(12,5);
```
Podane w ten sposób argumenty są kopiowane do funkcji, zatem funkcja może je zmienić wewnątrz siebie, ale nie to poza nią 
```cpp
int a = 2;
int b = 7;
void funkcja(int a, int b){
    a+=12;
    cout<<a+b<<endl;
}
funkcja(a,b);
cout<<a+b<<endl;
```
na ekranie pojawią się liczby
```
21
9
```
gdyż zmienna *a* nie została zmieniona poza funkcją<br>
Aby funkcja zmieniła nam zmienną możemy ją *linkować* w następujący sposób
```cpp
int x=12;
int y=55;
void funkcja(int& a, int& b){
    ...
}
funkcja(x. y);
```
Jak funkcja zwraca wynik to możemy jej wynik przypisać do zmiennej
```cpp
int funkcja(){
    return 12;
}
int a = funkcja();
```
Można też dodać domyślną wartość argumentu funkcji
```cpp
void funkcja(int a = 60, int b = 12){
    ...
}
funkcja();
```
### Rekurencja

Jeśli funkcja uruchamia samą siebie to nazywamy to rekurencją.<br>
Przy rekurencji trzeba uważać, żeby nie stworzyć niekończącej się pętli.<br>
Praktycznie zawsze szybiej będzie działał kod *nie-rekurencyjny* niż ten z rekurencją.<br>
Przykład na funkcji liczącej silni:
```cpp
int silnia(int n){ 
    if(n<2)
        return 1;
    return n*silnia(n-1);
}
```
Cała ta pętla uruchamiania samej siebie skończy się w momencie gdy n<2