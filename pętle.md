# Pętle
---

Pętle to potężne narzędzia, bez których programowanie byłoby o wiele cięższe. Niosą jednak ze sobą ryzyko zapętlenia się i programu który nie będzie się kończył.

---
### While
Pętla while zaczyna od sprawdzenia warunku i działa tak długo jak jest on prawdziwy
```cpp
int x = 0;
while(x<=8){
    cout<<x<<" ";
    x++;
}
```
output: 0 1 2 3 4 5 6 7 8
### Do while
Pętla najpierw robi co ma zrobić, a dopiero potem sprawdza warunek
```cpp
int x = 0;
do{
   cout<<x<<" ";
    x++; 
}while(x<=8);
```
output: 0 1 2 3 4 5 6 7 8 **9**<br>
Ważne również jest to, że tu po "while" musi być "**;**"
### For
Pętla przy której deklaracji ustalamy najwięcej rzeczy, co czasem uładnia kod
```cpp
for(int x = 0; x<=8; x++){
    cout<<x<<" ";
}
```
Jako pierwszy parametr dajemy zmienną kontrolującą ilość przebiegów pętli, później warunek do kontynuacji i na końcu akcję do wykonania pod koniec każdego przebiegu.