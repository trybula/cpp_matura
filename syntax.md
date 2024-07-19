# Syntax
---
C++ ma ściśle określony syntax, gdzie każda linia kodu musi się kończyć średnikiem, a *szkielet* kodu wygląda tak:
```cpp
#include<bits/stdc++.h>
using namespace std;
int main(){
    
return 0;
}
```
### Objaśnienie

- `#include<bits/stdc++.h>` załącza bibliotekę bits/stdc, która zawiera wszystkie podstawowe biblioteki
- `using namespade std;` ustala domyślną przestrzeń nazw, żeby nie musieć pisać np `std::cout<<'hi'`
- `int main()` to jest funkcja, która odpala się wraz z uruchomieniem programu
- `return 0;` zwraca 0 jako wynik wykonania programu, co oznacza, że wszystko wykonało się prawidłowo