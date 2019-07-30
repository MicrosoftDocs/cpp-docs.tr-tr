---
title: Başlatıcılar
ms.date: 07/29/2019
description: İçinde C++sınıfları, yapıları, dizileri ve temel türleri başlatma.
helpviewer_keywords:
- arrays [C++], array-element initializers
- aggregate initializers [C++]
ms.assetid: ce301ed8-aa1c-47b2-bb39-9f0541b4af85
ms.openlocfilehash: fd926177dd7540d8dc1e8512e9f17e20a0b8238c
ms.sourcegitcommit: 20a1356193fbe0ddd1002e798b952917eafc3439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68661610"
---
# <a name="initializers"></a>Başlatıcılar

Bir başlatıcı bir değişkenin başlangıç değerini belirtir. Değişkenleri şu bağlamlarda başlatabilirsiniz:

- Bir değişkenin tanımı içinde:

    ```cpp
    int i = 3;
    Point p1{ 1, 2 };
    ```

- Bir işlevin parametrelerinden biri olarak:

    ```cpp
    set_point(Point{ 5, 6 });
    ```

- Bir işlevin dönüş değeri olarak:

    ```cpp
    Point get_new_point(int x, int y) { return { x, y }; }
    Point get_new_point(int x, int y) { return Point{ x, y }; }
    ```

Başlatıcılar şu biçimleri alabilir:

- Parantez içinde bir ifade (veya virgülle ayrılmış ifadeler listesi):

    ```cpp
    Point p1(1, 2);
    ```

- Ardından bir ifade gelen bir eşittir işareti:

    ```cpp
    string s = "hello";
    ```

- Bir küme ayracıyla belirtilen başlatıcı listesi. Liste boş olabilir veya aşağıdaki örnekte olduğu gibi bir liste kümesinden oluşabilir:

    ```cpp
    struct Point{
        int x;
        int y;
    };
    class PointConsumer{
    public:
        void set_point(Point p){};
        void set_points(initializer_list<Point> my_list){};
    };
    int main() {
        PointConsumer pc{};
        pc.set_point({});
        pc.set_point({ 3, 4 });
        pc.set_points({ { 3, 4 }, { 5, 6 } });
    }
    ```

## <a name="kinds-of-initialization"></a>Başlatma türleri

Program yürütmesinde farklı noktalarda gerçekleşebilecek çeşitli başlatma türleri vardır. Farklı başlatma türleri birbirini dışlamaz, örneğin liste başlatma değer başlatmayı tetikleyebilir ve başka durumlarda da toplama başlatmayı tetikleyebilir.

### <a name="zero-initialization"></a>Sıfır başlatma

Sıfır başlatma, sıfır değerindeki bir değişken ayarının örtülü olarak şu türe dönüştürülmesidir:

- Sayısal değişkenler 0 olarak başlatılır (ya da 0.0 ya da 0.0000000000 vb.).

- Char değişkenleri olarak `'\0'`başlatılır.

- İşaretçiler **nullptr**olarak başlatılır.

- Diziler, [Pod](../standard-library/is-pod-class.md) sınıfları, yapılar ve birleşimler, üyelerine sıfır değer olarak başlatılmış.

Farklı zamanlarda sıfır başlatma gerçekleştirilir:

- Program başlangıcında, statik süresi olan tüm adlandırılmış değişkenler için. Bu değişkenler daha sonra yeniden başlatılmış olabilir.

- Değer başlatma sırasında, boş ayraçlar kullanılarak başlatılan skalar türler ve POD sınıf türleri için.

- Yalnızca üyelerinin başlattığu bir alt kümesi bulunan diziler.

Sıfır başlatma için bazı örnekler şunlardır:

```cpp
struct my_struct{
    int i;
    char c;
};

int i0;              // zero-initialized to 0
int main() {
    static float f1;  // zero-initialized to 0.000000000
    double d{};     // zero-initialized to 0.00000000000000000
    int* ptr{};     // initialized to nullptr
    char s_array[3]{'a', 'b'};  // the third char is initialized to '\0'
    int int_array[5] = { 8, 9, 10 };  // the fourth and fifth ints are initialized to 0
    my_struct a_struct{};   // i = 0, c = '\0'
}
```

### <a name="default_initialization"></a>Varsayılan başlatma

Sınıflar, yapılar ve birleşimler için varsayılan başlatma varsayılan bir oluşturucuyla başlatma. Varsayılan Oluşturucu, başlatma ifadesi olmadan veya **New** anahtar sözcüğüyle çağrılabilir:

```cpp
MyClass mc1;
MyClass* mc3 = new MyClass;
```

Sınıf, yapı veya birleşim varsayılan oluşturucuya sahip değilse, derleyici bir hata gösterir.

Skalar değişkenler, başlatma ifadesi olmadan tanımlandıklarında varsayılan olarak başlatılır. Belirsiz değerlere sahiptirler.

```cpp
int i1;
float f;
char c;
```

Diziler, başlatma ifadesi olmadan tanımlandıklarında varsayılan olarak başlatılır. Bir dizi varsayılan olarak başlatıldığında, üyeleri varsayılan olarak başlatılmış olur ve aşağıdaki örnekte olduğu gibi belirsiz değerlere sahiptir:

```cpp
int int_arr[3];
```

Dizi üyeleri varsayılan bir oluşturucuya sahip değilse, derleyici bir hata gösterir.

#### <a name="default-initialization-of-constant-variables"></a>Sabit değişkenlerin varsayılan başlatması

Sabit değişkenlerin bir başlatıcı ile birlikte bildirilmesi gerekir. Skalar türlerse, bir derleyici hatasına neden olur ve varsayılan bir oluşturucuya sahip sınıf türlerse bir uyarıya neden olur:

```cpp
class MyClass{};
int main() {
    //const int i2;   // compiler error C2734: const object must be initialized if not extern
    //const char c2;  // same error
    const MyClass mc1; // compiler error C4269: 'const automatic data initialized with compiler generated default constructor produces unreliable results
}
```

#### <a name="default-initialization-of-static-variables"></a>Statik değişkenlerin varsayılan başlatması

Başlatıcı olmadan belirtilen statik değişkenler 0 olarak başlatılır (örtük olarak türüne dönüştürülür).

```cpp
class MyClass {
private:
    int m_int;
    char m_char;
};

int main() {
    static int int1;       // 0
    static char char1;     // '\0'
    static bool bool1;   // false
    static MyClass mc1;     // {0, '\0'}
}
```

Genel statik nesnelerin başlatılması hakkında daha fazla bilgi için bkz. [ek başlatma konuları](../cpp/additional-startup-considerations.md).

### <a name="value-initialization"></a>Değer başlatma

Değer başlatma aşağıdaki durumlarda oluşur:

- adlandırılmış bir değer, boş küme ayracı başlatması kullanılarak başlatılır

- anonim bir geçici nesne, boş parantezler veya küme ayraçları kullanılarak başlatılır

- bir nesne **Yeni** anahtar sözcükle ve boş parantezlerle veya küme ayraçları ile başlatılır

Değer başlatma şunları yapar:

- en az bir ortak oluşturucuya sahip sınıflar için varsayılan Oluşturucu çağırılır

- tanımlı oluşturucuları olmayan birleşim olmayan sınıflar için, nesne sıfır olarak başlatılır ve varsayılan Oluşturucu çağırılır

- diziler için her öğe değer tarafından başlatılır

- diğer tüm durumlarda, değişken sıfır olarak başlatılır

```cpp
class BaseClass {
private:
    int m_int;
};

int main() {
    BaseClass bc{};     // class is initialized
    BaseClass*  bc2 = new BaseClass();  // class is initialized, m_int value is 0
    int int_arr[3]{};  // value of all members is 0
    int a{};     // value of a is 0
    double b{};  // value of b is 0.00000000000000000
}
```

### <a name="copy-initialization"></a>Kopyalama başlatması

Kopya başlatma, farklı bir nesne kullanan bir nesnenin başlatımı. Aşağıdaki durumlarda meydana gelir:

- bir değişken eşittir işareti kullanılarak başlatılır

- bir bağımsız değişken bir işleve geçirilir

- bir işlevden bir nesne döndürülür

- bir özel durum oluşturuldu veya yakalandı

- statik olmayan bir veri üyesi, eşittir işareti kullanılarak başlatılır

- sınıf, yapı ve birleşim üyeleri, toplu başlatma sırasında kopya başlatma tarafından başlatılır. Örnekler için bkz. [toplu başlatma](#agginit) .

Aşağıdaki kod, kopya başlatma için birkaç örnek gösterir:

```cpp
#include <iostream>
using namespace std;

class MyClass{
public:
    MyClass(int myInt) {}
    void set_int(int myInt) { m_int = myInt; }
    int get_int() const { return m_int; }
private:
    int m_int = 7; // copy initialization of m_int

};
class MyException : public exception{};
int main() {
    int i = 5;              // copy initialization of i
    MyClass mc1{ i };
    MyClass mc2 = mc1;      // copy initialization of mc2 from mc1
    MyClass mc1.set_int(i);    // copy initialization of parameter from i
    int i2 = mc2.get_int(); // copy initialization of i2 from return value of get_int()

    try{
        throw MyException();
    }
    catch (MyException ex){ // copy initialization of ex
        cout << ex.what();
    }
}
```

Kopya başlatma açık oluşturucuları çağıramıyor.

```cpp
vector<int> v = 10; // the constructor is explicit; compiler error C2440: cannot convert from 'int' to 'std::vector<int,std::allocator<_Ty>>'
regex r = "a.*b"; // the constructor is explicit; same error
shared_ptr<int> sp = new int(1729); // the constructor is explicit; same error
```

Bazı durumlarda, sınıfın kopya oluşturucusu silinmişse veya erişilemezse, kopya başlatma bir derleyici hatasına neden olur.

### <a name="direct-initialization"></a>Doğrudan başlatma

Doğrudan başlatma, (boş olmayan) kaşlı ayraçlar veya parantezler kullanılarak başlatma. Kopya başlatmanın aksine açık oluşturucuları çağırabilir: Aşağıdaki durumlarda meydana gelir:

- değişken boş olmayan küme ayraçları veya ayraçları ile başlatılır

- bir değişken **Yeni** anahtar sözcükle ve boş olmayan küme ayraçları veya parantezler ile başlatılır

- bir değişken **static_cast** ile başlatılır

- bir oluşturucuda, temel sınıflar ve statik olmayan üyeler bir başlatıcı listesiyle başlatılır

- bir lambda ifadesi içinde yakalanan bir değişkenin kopyasında

Aşağıdaki kod, doğrudan başlatmanın bazı örneklerini göstermektedir:

```cpp
class BaseClass{
public:
    BaseClass(int n) :m_int(n){} // m_int is direct initialized
private:
    int m_int;
};

class DerivedClass : public BaseClass{
public:
    // BaseClass and m_char are direct initialized
    DerivedClass(int n, char c) : BaseClass(n), m_char(c) {}
private:
    char m_char;
};
int main(){
    BaseClass bc1(5);
    DerivedClass dc1{ 1, 'c' };
    BaseClass* bc2 = new BaseClass(7);
    BaseClass bc3 = static_cast<BaseClass>(dc1);

    int a = 1;
    function<int()> func = [a](){  return a + 1; }; // a is direct initialized
    int n = func();
}
```

### <a name="list-initialization"></a>Liste başlatma

Bir değişken, bir örgü Başlatıcı listesi kullanılarak başlatıldığında liste başlatma gerçekleşir. Aşağıdaki durumlarda, örgü başlatıcı listeleri kullanılabilir:

- bir değişken başlatıldı

- **Yeni** anahtar sözcüğüyle bir sınıf başlatılır

- bir işlevden bir nesne döndürülür

- işleve geçirilen bir bağımsız değişken

- doğrudan başlatmada bağımsız değişkenlerden biri

- statik olmayan bir veri üyesi başlatıcısında

- bir Oluşturucu başlatıcı listesinde

Aşağıdaki kod, liste başlatmanın bazı örneklerini göstermektedir:

```cpp
class MyClass {
public:
    MyClass(int myInt, char myChar) {}
private:
    int m_int[]{ 3 };
    char m_char;
};
class MyClassConsumer{
public:
    void set_class(MyClass c) {}
    MyClass get_class() { return MyClass{ 0, '\0' }; }
};
struct MyStruct{
    int my_int;
    char my_char;
    MyClass my_class;
};
int main() {
    MyClass mc1{ 1, 'a' };
    MyClass* mc2 = new MyClass{ 2, 'b' };
    MyClass mc3 = { 3, 'c' };

    MyClassConsumer mcc;
    mcc.set_class(MyClass{ 3, 'c' });
    mcc.set_class({ 4, 'd' });

    MyStruct ms1{ 1, 'a', { 2, 'b' } };
}
```

### <a name="agginit"></a>Toplu başlatma

Toplama başlatma diziler veya sınıf türleri için (çoğunlukla yapılar veya birlikler) şunlara sahip olan bir liste başlatma biçimidir:

- özel veya korumalı üye yok

- açıkça varsayılan olarak ayarlanmış veya silinmiş oluşturucular dışında Kullanıcı tarafından sunulan oluşturucular yok

- temel sınıf yok

- sanal üye işlevi yok

> [!NOTE]
> <!--conformance note-->Visual Studio 2015 ve önceki sürümlerde, bir toplamanın statik olmayan üyeler için küme ayracı veya eşit başlatıcılara sahip olmasına izin verilmez. Bu kısıtlama, C++ 14 standardında kaldırılmıştır ve Visual Studio 2017 ' de uygulanır.

Toplama başlatıcıları, aşağıdaki örnekte olduğu gibi, bir eşittir işareti olan veya olmayan bir yerleşik başlatma listesinden oluşur:

```cpp
#include <iostream>
using namespace std;

struct MyAggregate{
    int myInt;
    char myChar;
};

struct MyAggregate2{
    int myInt;
    char myChar = 'Z'; // member-initializer OK in C++14
};

int main() {
    MyAggregate agg1{ 1, 'c' };
    MyAggregate2 agg2{2};
    cout << "agg1: " << agg1.myChar << ": " << agg1.myInt << endl;
    cout << "agg2: " << agg2.myChar << ": " << agg2.myInt << endl;

    int myArr1[]{ 1, 2, 3, 4 };
    int myArr2[3] = { 5, 6, 7 };
    int myArr3[5] = { 8, 9, 10 };

    cout << "myArr1: ";
    for (int i : myArr1){
        cout << i << " ";
    }
    cout << endl;

    cout << "myArr3: ";
    for (auto const &i : myArr3) {
        cout << i << " ";
    }
    cout << endl;
}
```

Aşağıdaki çıktıyı görmeniz gerekir:

```Output
agg1: c: 1
agg2: Z: 2
myArr1: 1 2 3 4
myArr3: 8 9 10 0 0
```

> [!IMPORTANT]
> Toplanan, ancak toplama başlatma sırasında açıkça başlatılmamış dizi üyeleri, `myArr3` yukarıdaki gibi sıfır olarak başlatılır.

#### <a name="initializing-unions-and-structs"></a>Birleşimler ve yapıları başlatma

Bir birleşimin Oluşturucusu yoksa, bunu tek bir değer (veya başka bir birleşim örneğiyle) başlatabilirsiniz. Değer, ilk statik olmayan alanı başlatmak için kullanılır. Bu, içinde ilk alanı başlatmak için kullanılan ilk değerin, ikinci alanı başlatmak için ikincinin vb. bulunduğu yapı başlatmadan farklıdır. Aşağıdaki örnekte birleşimler ve yapıların başlatılmasını karşılaştırın:

```cpp
struct MyStruct {
    int myInt;
    char myChar;
};
union MyUnion {
    int my_int;
    char my_char;
    bool my_bool;
    MyStruct my_struct;
};

int main() {
    MyUnion mu1{ 'a' };  // my_int = 97, my_char = 'a', my_bool = true, {myInt = 97, myChar = '\0'}
    MyUnion mu2{ 1 };   // my_int = 1, my_char = 'x1', my_bool = true, {myInt = 1, myChar = '\0'}
    MyUnion mu3{};      // my_int = 0, my_char = '\0', my_bool = false, {myInt = 0, myChar = '\0'}
    MyUnion mu4 = mu3;  // my_int = 0, my_char = '\0', my_bool = false, {myInt = 0, myChar = '\0'}
    //MyUnion mu5{ 1, 'a', true };  // compiler error: C2078: too many initializers
    //MyUnion mu6 = 'a';            // compiler error: C2440: cannot convert from 'char' to 'MyUnion'
    //MyUnion mu7 = 1;              // compiler error: C2440: cannot convert from 'int' to 'MyUnion'

    MyStruct ms1{ 'a' };            // myInt = 97, myChar = '\0'
    MyStruct ms2{ 1 };              // myInt = 1, myChar = '\0'
    MyStruct ms3{};                 // myInt = 0, myChar = '\0'
    MyStruct ms4{1, 'a'};           // myInt = 1, myChar = 'a'
    MyStruct ms5 = { 2, 'b' };      // myInt = 2, myChar = 'b'
}
```

#### <a name="initializing-aggregates-that-contain-aggregates"></a>Toplamaları içeren toplamaları başlatma

Toplam türler, dizi dizileri, yapı dizileri ve benzeri diğer toplama türlerini içerebilir. Bu türler, iç içe parantez kümesi kullanılarak başlatılır, örneğin:

```cpp
struct MyStruct {
    int myInt;
    char myChar;
};
int main() {
    int intArr1[2][2]{{ 1, 2 }, { 3, 4 }};
    int intArr3[2][2] = {1, 2, 3, 4};
    MyStruct structArr[]{ { 1, 'a' }, { 2, 'b' }, {3, 'c'} };
}
```

### <a name="reference-initialization"></a>Başvuru başlatma

Başvuru türündeki değişkenler, başvuru türünün türetildiği türden bir nesne ile veya başvuru türünün türetildiği türe dönüştürülebilen bir türde bir nesne ile başlatılmış olmalıdır. Örneğin:

```cpp
// initializing_references.cpp
int iVar;
long lVar;
int main()
{
    long& LongRef1 = lVar;        // No conversion required.
    long& LongRef2 = iVar;        // Error C2440
    const long& LongRef3 = iVar;  // OK
    LongRef1 = 23L;               // Change lVar through a reference.
    LongRef2 = 11L;               // Change iVar through a reference.
    LongRef3 = 11L;               // Error C3892
}
```

Geçici bir nesne ile başvuru başlatmanın tek yolu, sabit bir geçici nesneyi başlatmaktır. Başlatıldıktan sonra, bir başvuru türü değişkeni her zaman aynı nesneye işaret eder; başka bir nesneyi işaret etmek için değiştirilemez.

Söz dizimi aynı olsa da, başvuru türü değişkenlerinin başlatılması ve başvuru türü değişkenlerine atanması anlam olarak farklılık görebilir. Önceki örnekte, değişen `iVar` ve `lVar` başlatmaları gibi görünen atamalar, ancak farklı etkileri vardır. Başlatma, başvuru türü değişkenin işaret ettiği nesneyi belirtir; atama, başvuru aracılığıyla başvurulan nesnesine atar.

Hem başvuru türünün bir bağımsız değişkenini bir işleve geçirme hem de bir işlevden başvuru türü değeri döndürme nedeniyle, döndürülen başvurular gibi bir işleve biçimsel bağımsız değişkenler doğru şekilde başlatılır.

Başvuru türü değişkenleri yalnızca, başlatıcılar olmadan bildirilemez:

- İşlev bildirimleri (prototürler). Örneğin:

    ```cpp
    int func( int& );
    ```

- İşlev dönüş türü bildirimleri. Örneğin:

    ```cpp
    int& func( int& );
    ```

- Başvuru türü sınıf üyesinin bildirimi. Örneğin:

    ```cpp
    class c {public:   int& i;};
    ```

- Açıkça **extern**olarak belirtilen bir değişken bildirimi. Örneğin:

    ```cpp
    extern int& iVal;
    ```

Bir başvuru türü değişkeni başlatırken, derleyici bir nesneye başvuru oluşturma veya başvurunun işaret ettiği geçici bir nesne oluşturma arasında seçim yapmak için aşağıdaki şekilde gösterilen karar grafiğini kullanır.

![Başvuru türlerinin başlatılması Için karar grafiği](../cpp/media/vc38s71.gif "Başvuru türlerinin başlatılması Için karar grafiği") <br/>
Başvuru türlerinin başlatılması için karar grafiği

**Geçici** türlere ( **geçici** *TypeName* <strong>&</strong> *tanımlayıcısı*olarak belirtilen) yapılan başvurular, aynı türdeki **geçici** nesnelerle veya **geçici** olarak bildirilmemiş nesnelerle başlatılabilir . Ancak, bu tür **const** nesneleriyle başlatılamaz. Benzer şekilde, **const** türlerine yapılan başvurular ( **const** *TypeName* <strong>&</strong> *tanımlayıcısı*olarak bildirilmiştir) aynı türdeki **const** nesneleriyle (veya bu türe ya da nesnelerle dönüştürmeye sahip olan herhangi bir şekilde) başlatılabilir **const**olarak bildirilmemiş). Ancak, bu türdeki **geçici** nesnelerle başlatılamaz.

**Const** veya **volatile** anahtar sözcüğü ile nitelenen başvurular yalnızca **const** veya **volatile**olarak belirtilen nesneler ile başlatılabilir.

### <a name="initialization-of-external-variables"></a>Dış değişkenlerin başlatılması

Otomatik, statik ve dış değişkenlerin bildirimleri başlatıcılar içerebilir. Ancak, dış değişkenlerin bildirimleri yalnızca değişkenler **extern**olarak bildirilmemiş ise başlatıcılar içerebilir.