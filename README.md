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

## Constructor
```cpp
class  Wall {
  public:
    // create a constructor
    Wall() {
      // code
    }
};
```

## Constructor Overloading

```cpp
class Sinif {
	public:
		int x;
		Sinif(int a) {
			x = 3*a;
		}
		Sinif(double a) {
			x = 2*a;
		}
};

int main(){
	Sinif M(10);
	cout << "Constructor (INT): " << M.x;
	
	Sinif S(10.5);
	cout << "\nConstructor (DOUBLE): " << S.x;
}
```


## Objeler ve Fonksiyonlar
```cpp
class Student {

   public:
    double marks;

    Student(double m) {
        marks = m;
    }
};

void calculateAverage(Student s1, Student s2) {

    double average = (s1.marks + s2.marks) / 2;

   cout << "Average Marks = " << average << endl;

}

int main() {
    Student student1(88.0), student2(56.0);

   calculateAverage(student1, student2);

    return 0;
}
```

## Return Object
```cpp
class Student {
   public:
    double marks1, marks2;
};

// function that returns object of Student
Student createStudent() {
    Student student;

    // Initialize member variables of Student
    student.marks1 = 96.5;
    student.marks2 = 75.0;

    // print member variables of Student
    cout << "Marks 1 = " << student.marks1 << endl;
    cout << "Marks 2 = " << student.marks2 << endl;

    return student;
}

int main() {
    Student student1;

    // Call function
    student1 = createStudent();

    return 0;
}
```

## Operator Overloading
> `Bu kod blogumuzda Sinif clasında yer alan operator alanına göz atarsak, yine aynı class'ta yer alan birinci parametreye gönderme yapılmış. Yani gelen 2 değer x ve y'ye atanmış ve geri döndürülmüş. Bu da demek oluyor ki operator - olarak belirlediğimiz alan bize eksi verileri döndürecek. O zaman main alanına gelerek M ve S adında iki tane sınıf oluşturuyoruz ve M sınıfımızın x ve y değerlerini constructor yardımı ile sırasıyla 10 ve 20 yapıyoruz. Fakat S sınıfına geldiğimizde -M sınıfını gönderiyoruz. Bu durumda operator - işleme giriyor ve sonucunda bize eksili olarak x ve y değerlerini S sınıfına atamış oluyor.` 


```cpp
class Sinif {
	public:
		int x;
		int y;
		Sinif(int a, int b) {
			x = a;
			y = b;
		}
		Sinif operator - (){
			return Sinif(-x, -y); 
		}
};

int main(){
	Sinif M(10,20);
	Sinif S = -M;
	
	cout << "M Fonksiyonu (x): " << M.x;
	cout << "\nM Fonksiyonu (y): " << M.y;
	cout << "\nS Fonksiyonu (x): " << S.x;
	cout << "\nS Fonksiyonu (y): " << S.y;
}
```

## Operator Overloading #2
```cpp
class className {
    ... .. ...
    public
       returnType operator symbol (arguments) {
           ... .. ...
       } 
    ... .. ...
};
```

## Operator Overloading #2
```cpp
class Count {
   private:
    int value;

   public:

    // Constructor to initialize count to 5
    Count() : value(5) {}

    // Overload ++ when used as prefix
    void operator ++ () {
        ++value;
    }

    void display() {
        cout << "Count: " << value << endl;
    }
};

int main() {
    Count count1;

    // Call the "void operator ++ ()" function
    ++count1;

    count1.display();
    return 0;
}
```

## Prefix - Postfix
> `Onceki ornekler operatorumuz prefix olarak kullanildiginda calismakta. Operatoru postfix yapmak istiyorsak alttaki syntaxi kullanmaliyiz.`

```cpp
void operator ++ (int) {
    // code
}
```
>`Parantezin icersindeki `int` degerine bakin. Bu unary operatorleri postfix olarak kullanmak icin kullanilan syntaxtir, fonksiyon degil.` 

## Prefix ve Postfix operator ornegi
```cpp
#include <iostream>
using namespace std;

class Count {
   private:
    int value;

   public:

    // Constructor to initialize count to 5
    Count() : value(5) {}


    // Overload ++ when used as prefix
    void operator ++ () {
        ++value;
    }


    // Overload ++ when used as postfix
    void operator ++ (int) {
        value++;
    }

    void display() {
        cout << "Count: " << value << endl;
    }
};

int main() {
    Count count1;

    // Call the "void operator ++ (int)" function
    count1++;
    count1.display();

    // Call the "void operator ++ ()" function
    ++count1;

    count1.display();
    return 0;
}
```
> Output
```
Count: 6
Count: 7
```
## Bilgi
> `Yukaridaki ornek hem postfix hem de prefix olarak calismakta, fakat asagidaki gibi bir sey denersek;`
```cpp
Count count1, result;

// Error
result = ++count1;
```
> `Hata verecektir. Bunun nedeni fonksiyonumuzun return tipi void'dir. Bu problemi fonksiyonun return tipini Count olarak degistirerek cozebiliriz.`

## Return Degiskenli Operator fonksiyonu
```cpp

class Count {
   private:
    int value;

   public:
    // Constructor to initialize count to 5
    Count() : value(5) {}

    // Overload ++ when used as prefix
    Count operator ++ () {
        Count temp;

        // Here, value is the value attribute of the calling object
        temp.value = ++value;

        return temp;
    }

    // Overload ++ when used as postfix
    Count operator ++ (int) {
        Count temp;

        // Here, value is the value attribute of the calling object
        temp.value = value++;

        return temp;
    }

    void display() {
        cout << "Count: " << value << endl;
    }
};

int main() {
    Count count1, result;

    // Call the "Count operator ++ ()" function
    result = ++count1;
    result.display();

    // Call the "Count operator ++ (int)" function
    result = count1++;
    result.display();

    return 0;
}
```

## Binary Operator Overloading
```cpp
class Sinif{
    private:
        int sayi1;
        int sayi2;
        int toplam;
    public:
    
    Sinif(): sayi1(0) , sayi2(0) {}

    void girdi(){
        cout << "Iki sayi giriniz: ";
        cin >> sayi1;
        cin >> sayi2;
    }
    // Ayni zamanda const kullanimi operator fonkisoyunun "sinif2"'yi degistirmekten korur.  
    Sinif operator + (const Sinif& obj){ // Burada "Sinif&" kullanimi kodumuzu daha verimli kilar. Operator fonksiyonunun icerisinde kopyalama yapmak yerine bunu yonlendirir.
        Sinif temp;     
        temp.sayi1 = sayi1 + sayi2;
        temp.sayi2 = obj.sayi1 + obj.sayi2;
        temp.toplam = temp.sayi1 + temp.sayi2;
        return temp;
    }
    
    void cikti(){
        cout << toplam << endl;
    }
};

int main(){
    Sinif sinif1 , sinif2, sonuc;

    sinif1.girdi();
    sinif2.girdi();
    sonuc = sinif1 + sinif2;
    sonuc.cikti();
}
```
