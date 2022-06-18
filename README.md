# C++


>`const` veri tipi degistirilemez.

## I/O Stream
```cpp
#include <iostream> // input/output header
using namespace std; 
```

## Cout
```cpp
cout << num1 << endl; // endl means new line
cout << num1 << endl ; // that's l (el) , not one (1)
cout << "character:" << ch << endl;
cout << "Hello world\n" ;
```

## std::cout 
> Eger `using namespace std` durumunu entegre etmeseydik, `cout` yerine `std::cout` kullanmamiz gerekirdi.

## Cin
```cpp
cin >> num;
cout << "The number is: " << num;
```

## std::cin
> Eger `std` namespace'ini entegre etmeseydin, `cin` yerine `std::cin` kullanmamiz gerekirdi.

## Veri Tipi Donusturme

> Implict Conversion
```cpp
num_double = num_int;
```

> Explicit Conversion
1. C-Style - Cast Notation
```cpp
num_double = (double)num_int;
```
2. Function Style Casting
```cpp
num_double = double(num_int);
```

## Tek Satirda If-Else ?:
```cpp
string result = (5 > 0) ? "even" : "odd"; 
```

## sizeof()
> Veri tipinin boyutunu gosterir.
```cpp
sizeof(int);
```

## Bellek Adresi
> `&` isareti verinin bellekteki adresini temsil eder.
```cpp
&num;
```

## Struct degiskenlerindeki uyelere erisme
> `.`
```cpp
s1.mark = 92;
```

## Pointer ile class ya da struct degiskenlerine erisme
```cpp
ptr->marks = 92;
```

## For Dongusu
```cpp
for (variable : collection) {
    // body of loop
}
```

## Goto durumu
```
goto statement
goto label;
... .. ...
... .. ...
... .. ...
label: 
statement;
... .. ...
```

## Array olusturma
```cpp
int x[6] = {19, 10, 8, 17, 9, 15};
```

## C-String tanimlama
```cpp
char str[] = "C++";
```
> Yukaridaki `str` degiskeni `4` karakter tutmakta, stringin sonunda bir `\0` denilen bir null karakter bulunmakta.

> Alternatif yollar;
```cpp
char str[4] = "C++";
char str[] = {'C','+','+','\0'};
char str[4] = {'C','+','+','\0'};
```

## Kullanicidan girilen tum satiri okuma ve yazdirma
```cpp
cin.get(str, 100);
```
> Ilk arguman string degiskeninin adi, ikincisi ise arrayin maksimum boyutu.

## Veri Turu String
```cpp
string str;
getline(cin, str);
```

## Structer
```cpp
struct Person
{
    char name[50];
    int age;
    float salary;
};

int main()
{
    Person p1;
    cin.get(p1.name, 50);
    cin >> p1.age;
    cin >> p1.salary;
}
```

## Structer ve Fonksiyon
```cpp
struct Person
{
    char name[50];
    int age;
    float salary;
};

int main() {
    Person p;
    displayData(p);
}

void displayData(Person p){
    cout << "Name: " << p.name << endl;
}
```

## Numaralandirma
```cpp
enum week { Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday };

int main()
{
    week today;
    today = Wednesday;
    cout << "Day " << today+1;
    return 0;
}
```

## Class'lar ve Objeler
```cpp
class Room {
    public:
        double length;
        double breadth;
        double height;   

        double calculateArea(){   
            return length * breadth;
        }

        double calculateVolume(){   
            return length * breadth * height;
        }
};

int main(){
    Room room1;
    int sum;
    cin >> room1.length;
    cout << room1.length << endl;
}
```