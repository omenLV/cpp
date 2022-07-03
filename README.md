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

## Pointer
> Pointerlar, diger degiskenlerin bellekteki adreslerini tutan degiskenlerdir.
> Eger programimizda `var` adinda bir degisken bulunuyorsa, `&var` bu degiskenin belleteki adresini bize verir.
```cpp
int main(){
    int var = 5;
    cout << "Memory address of `var` variable "<< &var << endl;
    
}
```

## Pointer Olusturmak
```cpp
int* pointVar; // preferred syntax
```

## Pointera adres atama
```cpp
int* pointVar, var;
var = 5;

// var degiskeninin adresi pointVar'a atandi
pointVar = &var;
```

## Pointerlar tarafindan isaretlenen adresi degistirme
```cpp
int var = 5;
int* pointVar;

// assign address of var
pointVar = &var;

// change value at address pointVar
*pointVar = 1;

cout << var << endl; // Output: 1
```

## Pointerlar tarafindan isaretlenen adresi degistirme 2#
```cpp
int main() {
    int var = 5;
    int* pointVar;

    // store address of var
    pointVar = &var;

    // print var
    cout << "var = " << var << endl;

    // print *pointVar
    cout << "*pointVar = " << *pointVar << endl
         << endl;

    cout << "Changing value of var to 7:" << endl;

    // change value of var to 7
    var = 7;

    // print var
    cout << "var = " << var << endl;

    // print *pointVar
    cout << "*pointVar = " << *pointVar << endl
         << endl;

    cout << "Changing value of *pointVar to 16:" << endl;

    // change value of var to 16
    *pointVar = 16;

    // print var
    cout << "var = " << var << endl;

    // print *pointVar
    cout << "*pointVar = " << *pointVar << endl;
    return 0;
}
```

## Pointerlar ve Arrayler
```cpp
int *ptr;
int arr[5];

// store the address of the first
// element of arr in ptr
ptr = arr;
```
> Ya da...

```cpp
int *ptr;
int arr[5];
ptr = &arr[0];
```

## Her bir Array degerini Isaretleme
```cpp
int *ptr;
int arr[5];
ptr = arr;

ptr + 1 is equivalent to &arr[1];
ptr + 2 is equivalent to &arr[2];
ptr + 3 is equivalent to &arr[3];
ptr + 4 is equivalent to &arr[4];
```
> Ya da;
```cpp
*ptr == arr[0];
*(ptr + 1) is equivalent to arr[1];
*(ptr + 2) is equivalent to arr[2];
*(ptr + 3) is equivalent to arr[3];
*(ptr + 4) is equivalent to arr[4];
```

## Pointer & Array Ornek
```cpp
int main()
{
    float arr[3];

    // pointer degiskeni tanimlama
    float *ptr;
    
    cout << "Array kullanarak elementlerin bellek adresleri: " << endl;

    // array elementlerinin adresinlerini yazdiran for dongusu
    for (int i = 0; i < 3; ++i)
    {
        cout << "&arr[" << i << "] = " << &arr[i] << endl;
    }

    // ptr = &arr[0]
    ptr = arr;

    cout<<"\nPointer kullanarak array adresi: "<< endl;

    for (int i = 0; i < 3; ++i)
    {
        cout << "ptr + " << i << " = "<< ptr + i << endl;
    }

    return 0;
}
```
## Array ismini Pointer olarak kullanma
> Array degiskeninin ismi, o dizinin ilk elementini isaret eder. Yani bir diziyi isaretci gibi davrandirtabiliriz.
```cpp
int main() {
    float arr[5];
    
   // Insert data using pointer notation
    cout << "Enter 5 numbers: ";
    for (int i = 0; i < 5; ++i) {

        // store input number in arr[i]
        cin >> *(arr + i) ;

    }

    // Display data using pointer notation
    cout << "Displaying data: " << endl;
    for (int i = 0; i < 5; ++i) {

        // display value of arr[i]
        cout << *(arr + i) << endl ;

    }

    return 0;
}
```

## Fonksiyona Pointer ile arguman gonderme
```cpp

void func1(int numVal) {
    // code
}


// & ile parametre aliyor
void func2(int &numRef) {
    // code
}

int main() {
    int num = 5;

    // deger ile arguman
    func1(num);

    // pointer ile referans vererek arguman
    func2(num);

    return 0;
}
```

## Pointersiz Fonksiyona Referans Gonderme
```cpp
// function definition to swap values
void swap(int &n1, int &n2) {
    int temp;
    temp = n1;
    n1 = n2;
    n2 = temp;
}

int main()
{

    // initialize variables
    int a = 1, b = 2;

    cout << "Before swapping" << endl;
    cout << "a = " << a << endl;
    cout << "b = " << b << endl;

    // call function to swap numbers
    swap(a, b);

    cout << "\nAfter swapping" << endl;
    cout << "a = " << a << endl;
    cout << "b = " << b << endl;

    return 0;
}
```

## Pointer Kullanarak Referans Gonderme
```cpp
void swap(int*, int*);

int main()
{

    // initialize variables
    int a = 1, b = 2;

    cout << "Before swapping" << endl;
    cout << "a = " << a << endl;
    cout << "b = " << b << endl;

    // call function by passing variable addresses
    swap(&a, &b);

    cout << "\nAfter swapping" << endl;
    cout << "a = " << a << endl;
    cout << "b = " << b << endl;
    return 0;
}

// function definition to swap numbers
void swap(int* n1, int* n2) {
    int temp;
    temp = *n1;
    *n1 = *n2;
    *n2 = temp;
}
```

## Bellek Yonetimi
### New Operatoru
```cpp
// declare an int pointer
int* pointVar;

// dynamically allocate memory
// using the new keyword 
pointVar = new int;

// assign value to allocated memory
*pointVar = 45;
```
> Bu kod blogunda, bir integer degiskeni icin `new` kullanarak dinamik olarak bellek ayirdik. Bunun icin bir pointer kullandik, bunun nedeni `new` operatoru bize bellek konumunun adresini dondurur.

> Bir `Array` olmasi durumunda, `new` operatoru Array'in ilk elementinin adresini dondurur.

> New Operatoru icin Syntax;
```cpp
pointerVariable = new dataType;
```

### Delete Operatoru
> Dinamik olarak bellek uzerinden ayirdigimiz bir degiskeni kullanmamiza daha fazla ihtiyacimizin olmadigi durumlarda degisken ile kullanilan bellegi serbest birakabiliriz. Bunun icin, `delete` operatoru kullanilir. Bu operator, bellegi isletim sistemine geri gonderir.

> Ayni zamanda bu, `memory deallocation` olarak bilinir.
> Syntax'i;
```cpp
delete pointerVariable;
```
> Ornek kod;
```cpp
// pointer tanimi
int* pointVar;

// tam sayi degiskeni icin dinamik olarak bellek tahsili
pointVar = new int;

// degisken bellege deger atama
*pointVar = 45;

// bellekte saklanan degeri dondurme
cout << *pointVar; // Output: 45

// tahsil edilmis bellegi serbest birakma
delete pointVar;
```

## Array'ler icin New ve Delete
```cpp
int main(){  
  int num;
  cout << "Enter total number of students: ";
  cin >> num;
  float* ptr;
    
  // memory allocation of num number of floats
  ptr = new float[num];

  cout << "Enter GPA of students." << endl;
  for (int i = 0; i < num; ++i) {
    cout << "Student" << i + 1 << ": ";
    cin >> *(ptr + i);
  }

  cout << "\nDisplaying GPA of students." << endl;
  for (int i = 0; i < num; ++i) {
    cout << "Student" << i + 1 << ": " << *(ptr + i) << endl;
  }

  // ptr memory is released
  delete[] ptr;

  return 0;
}
```

## Objeler ile New ve Delete operatorleri
```cpp

class Student {
  private:
    int age;

  public:

    // constructor initializes age to 12
    Student() : age(12) {}

    void getAge() {
      cout << "Age = " << age << endl;
    }
};

int main() {

  // dynamically declare Student object
  Student* ptr = new Student();

  // call getAge() function
  ptr->getAge();

  // ptr memory is released
  delete ptr;

  return 0;
}
```

## Inheritance
> Inheritance, bir class tarafindan (base class) turemis bir class (derived class) olusturmamizi saglar.
```cpp
class Animal {
    // eat() function
    // sleep() function
};

class Dog : public Animal {
    // bark() function
};
```

## is-a relationship | IS-A
> Inheritance bir IS-A'dir. Inheritance sadece iki sinif arasinda bir iliski varsa kullanilir, ornegin;
+ Araba bir aractir..
+ Portakal bir meyvedir.
+ Cerrah bir doktordur.
+ Kopek bir hayvandir.

> Ornek kod;
```cpp
class Animal {

   public:
    void eat() {
        cout << "I can eat!" << endl;
    }

    void sleep() {
        cout << "I can sleep!" << endl;
    }
};

// derived class
class Dog : public Animal {
 
   public:
    void bark() {
        cout << "I can bark! Woof woof!!" << endl;
    }
};

int main() {
    // Create object of the Dog class
    Dog dog1;

    // Calling members of the base class
    dog1.eat();
    dog1.sleep();

    // Calling member of the derived class
    dog1.bark();

    return 0;
}
```

## Protected Members
> Protected, ayni Private gibi sadece class'in icindeki uyeler tarafindan erisilebilen bir access modifier'dir. Ancak Private'in aksine, protected turemis (derived) siniflar tarafindan da kullanilabilir. Fakat private'da bu soz konusu degildir.

## Access Modifier Ornek
```cpp
class Animal {
    // code
};

class Dog : private Animal { // private
    // code
};

class Cat : protected Animal { // protected
    // code
};
```
> Buradaki kodda, birkac ozellik bulunmakta

+ Eger bir derived class `public` olarak tanimlanirsa, base class'in uyeleri derived class uyeleri tarafindan kullanilabilir.

+ Eger bir derived class `private` olarak tanimlanirsa, base class'in tum uyeleri derived class icin private, yani erisilemez olur.

+ Eger bir derived class `protected` olarak tanimlanirsa, base class'in tum uyeleri derived icin protected olur.

+ Dipnot; Bir base class'in tum `private` uyeleri derived class icin `private`'dir.

## Function Overriding
> Derived class'ta ve Base class'ta ayni isme ve argumanlara sahip iki tane fonksiyon olusturulur ve cagirilirsa Base class'taki fonkisiyon `override` edilir ve Derived class'taki fonksiyon calistirilir. 

```cpp
class Base {
   public:
    void print() {
        cout << "Base Function" << endl;
    }
};

class Derived : public Base {
   public:
    void print() {
        cout << "Derived Function" << endl;
    }
};

int main() {
    Derived derived1;
    derived1.print();
    return 0;
}
```

```
Output: Derived Function
```

> Eger bu sekilde obje olusturulursa;
```cpp
// Call function of Base class
Base base1;
base1.print(); // Output: Base Function
```
> Fonksiyon override edilmez.

## Override edilmis Base fonksiyonun erisme
```cpp
class Base {
   public:
    void print() {
        cout << "Base Function" << endl;
    }
};

class Derived : public Base {
   public:
    void print() {
        cout << "Derived Function" << endl;
    }
};

int main() {
    Derived derived1, derived2;
    derived1.print();

    // access print() function of the Base class
    derived2.Base::print();

    return 0;
}
```

```cpp
derived2.Base::print();
```

## Derived Class uzerinden Override edilmis fonksiyonu cagirma
```cpp
class Base {
   public:
    void print() {
        cout << "Base Function" << endl;
    }
};

class Derived : public Base {
   public:
    void print() {
        cout << "Derived Function" << endl;

        // call overridden function
        Base::print();
    }
};

int main() {
    Derived derived1;
    derived1.print();
    return 0;
}
```

## Override edilmis fonksiyonu Pointer ile cagirma
```cpp

class Base {
   public:
    void print() {
        cout << "Base Function" << endl;
    }
};

class Derived : public Base {
   public:
    void print() {
        cout << "Derived Function" << endl;
    }
};

int main() {
    Derived derived1;

    // pointer of Base type that points to derived1
    Base* ptr = &derived1;

    // call function of Base class using ptr
    ptr->print();

    return 0;
}
```

> Bu kod blogunda Base tipi `ptr` adinda bir pointer olusturduk. Bu pointer, Derived objesi olan `derived1`'i isaretler. Bu yuzden eger `ptr` Derived objesine isaretli olsa bile, aslinda `Base` tipidir. Yani Base'in member fonksiyonunu cagirir.

## Multilevel Inheritance
```cpp
class A { 
... .. ... 
};
class B: public A {
... .. ...
};
class C: public B {
... ... ...
};
```

> Ornek kod;
```cpp
class A {
    public:
      void display() {
          cout<<"Base class content.";
      }
};

class B : public A {};

class C : public B {};

int main() {
    C obj;
    obj.display();
    return 0;
}
```


## Multiple Inheritance
> C++'da bir class birden fazla parent classtan derived edilmis olabilir. Ornegin, `Yarasa` adindaki bir class, base class olan `Memeli` ve `Kanatli` siniflarindan Derived edilmis olabilir. Bu mantikli bir davranis olur, cunku yarasa hem kanatli hem de memeli bir hayvandir.

```cpp
class Mammal {
  public:
    Mammal() {
      cout << "Mammals can give direct birth." << endl;
    }
};

class WingedAnimal {
  public:
    WingedAnimal() {
      cout << "Winged animal can flap." << endl;
    }
};

class Bat: public Mammal, public WingedAnimal {};

int main() {
    Bat b1;
    return 0;
}
```

## Multiple Inheritance Belirsizligi

> Multiple Inheritance'daki acik ara sorun, function onverriding'tir. Ornegin, iki base class dervired class icinde override edilemeyen iki adet ayni fonksiyona sahip. Eger bunu cagirmaya calisirsak, derleyici hta verir. Cunku derleyici hangi fonksiyonu calistiracagini bilemez. 

```cpp
class base1 {
  public:
      void someFunction( ) {....}  
};
class base2 {
    void someFunction( ) {....} 
};
class derived : public base1, public base2 {};

int main() {
    derived obj;
    obj.someFunction() // Error!  
}
```

> Bunu cozmek icin;
```cpp
int main() {
    obj.base1::someFunction( );  // Function of base1 class is called
    obj.base2::someFunction();   // Function of base2 class is called.
}
```

## Hierarchical Inheritance

> Eger birden fazla class base classtan turemis ise, bu hiyerarsik inheritance olarak adlandirilir. 

+ Ornegin, Fizik, Kimya, Biyoloji = Fen
+ Benzer olarak, Kopek, kedi, at ise hayvan class'indan turemis siniflardir.

> Syntax
```cpp
class base_class {
     ... .. ...
}

class first_derived_class: public base_class {
     ... .. ...
}

class second_derived_class: public base_class {
     ... .. ...
}

class third_derived_class: public base_class {
     ... .. ...
}
```

## Friend Function
> Friend function, bir class'in protected ve private verilerine erisebilir. Tanimlama syntaxi;
```cpp
class className {
    ... .. ...
    friend returnType functionName(arguments);
    ... .. ...
}
```

> Ornek kod;
```cpp
class ClassB;

class ClassA {
    
    public:
        // constructor to initialize numA to 12
        ClassA() : numA(12) {}
        
    private:
        int numA;
        
         // friend function declaration
         friend int add(ClassA, ClassB);
};

class ClassB {

    public:
        // constructor to initialize numB to 1
        ClassB() : numB(1) {}
    
    private:
        int numB;
 
        // friend function declaration
        friend int add(ClassA, ClassB);
};

// access members of both classes
int add(ClassA objectA, ClassB objectB) {
    return (objectA.numA + objectB.numB);
}

int main() {
    ClassA objectA;
    ClassB objectB;
    cout << "Sum: " << add(objectA, objectB);
    return 0;
}
```

> Bu programda ClassA ve ClassB `add()` fonksiyonunu friend function olarak tanimladi. Yani, bu fonksiyon iki sinifinda private verilerine erisebilir.

> Hatirlanmasi gereken bir sey de, ClassA icindeki friend function ClassB'yi kullaniyor.

> Bu noktada, ClassB tanimlanmamis.

```cpp
// inside classA 
friend int add(ClassA, ClassB);
```

> Bunun calismasi icin, ClassB'nin forward declaration'ina ihtiyacimiz var. 
```cpp
// forward declaration
class ClassB;
```

## Friend Class
```cpp
class ClassB;

class ClassA {
   // ClassB is a friend class of ClassA
   friend class ClassB;
   ... .. ...
}

class ClassB {
   ... .. ...
}
```
> ClassB, ClassA'nin friend class'i. ClassA'nin tum uyelerine erisim saglayabilir. Fakat ClassA icerisinden ClassB'nin uyelerine erisemeyiz.

+ Ornek kod;
```cpp
class ClassB;

class ClassA {
    private:
        int numA;

        // friend class declaration
        friend class ClassB;

    public:
        // constructor to initialize numA to 12
        ClassA() : numA(12) {}
};

class ClassB {
    private:
        int numB;

    public:
        // constructor to initialize numB to 1
        ClassB() : numB(1) {}
    
    // member function to add numA
    // from ClassA and numB from ClassB
    int add() {
        ClassA objectA;
        return objectA.numA + numB;
    }
};

int main() {
    ClassB objectB;
    cout << "Sum: " << objectB.add();
    return 0;
}
```
