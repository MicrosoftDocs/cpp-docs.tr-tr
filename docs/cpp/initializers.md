---
title: Başlatıcılar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- array-element initializers
- initializing arrays [C++], initializers
- arrays [C++], array-element initializers
- declarators, as initializers
- initializers, array element
ms.assetid: ce301ed8-aa1c-47b2-bb39-9f0541b4af85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b7a94ee7df512262c58d7a90e3dbf461270b5d4c
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939875"
---
# <a name="initializers"></a>Başlatıcılar
Bir başlatıcı bir değişkenin başlangıç değerini belirtir. Değişkenleri şu bağlamlarda başlatabilirsiniz:  
  
-   Bir değişkenin tanımı içinde:  
  
    ```cpp  
    int i = 3;  
    Point p1{ 1, 2 };  
    ```  
  
-   Bir işlevin parametrelerinden biri olarak:  
  
    ```cpp  
    set_point(Point{ 5, 6 });  
    ```  
  
-   Bir işlevin dönüş değeri olarak:  
  
    ```cpp  
    Point get_new_point(int x, int y) { return { x, y }; }  
    Point get_new_point(int x, int y) { return Point{ x, y }; }  
  
    ```  
  
 Başlatıcılar şu biçimleri alabilir:  
  
-   Parantez içinde bir ifade (veya virgülle ayrılmış ifadeler listesi):  
  
    ```cpp  
    Point p1(1, 2);  
    ```  
  
-   Ardından bir ifade gelen bir eşittir işareti:  
  
    ```cpp  
    string s = "hello";  
    ```  
  
-   Bir küme ayracıyla belirtilen başlatıcı listesi. Liste boş olabilir veya listeleri, aşağıdaki örnekte olduğu gibi bir dizi oluşabilir:  
  
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
  
-   Sayısal değişkenler 0 olarak başlatılır (ya da 0.0 ya da 0.0000000000 vb.).  
  
-   Char değişkenleri başlatıldığı `'\0'`.  
  
-   İşaretçileri başlatıldığı `nullptr`.  
  
-   Diziler, [POD](../standard-library/is-pod-class.md) sınıflar, yapılar ve birleşimlerin bir sıfır değeri olarak başlatılan üyeleri vardır.  
  
 Farklı zamanlarda sıfır başlatma gerçekleştirilir:  
  
-   Program başlangıcında, statik süresi olan tüm adlandırılmış değişkenler için. Bu değişkenler daha sonra yeniden başlatılmış olabilir.  
  
-   Değer başlatma sırasında, boş ayraçlar kullanılarak başlatılan skalar türler ve POD sınıf türleri için.  
  
-   Yalnızca üyelerinin başlattığu bir alt kümesi bulunan diziler.  
  
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
  
### <a name="default_initialization"></a> Varsayılan başlatma  
 Sınıflar, yapılar ve birleşimler için varsayılan başlatma varsayılan bir Oluşturucu ile başlatma ' dir. Varsayılan oluşturucu veya hiçbir başlatma ifadesi ile çağrılabilir **yeni** anahtar sözcüğü:  
  
```cpp  
MyClass mc1;  
MyClass* mc3 = new MyClass;  
```  
  
 Sınıf, yapı veya birleşim varsayılan oluşturucuya sahip değilse, derleyici bir hata gösterir.  
  
 Skaler değişkenleri, hiçbir başlatma ifadesiyle tanımlandıklarında varsayılan kullanılabilir. Belirsiz değerlere sahiptirler.  
  
```cpp  
int i1;  
float f;  
char c;  
```  
  
 Hiçbir başlatma ifadesiyle tanımlandıklarında varsayılan dizilerdir. Bir dizi varsayılan olarak başlatıldığında, üyeleri varsayılan ve aşağıdaki örnekte olduğu gibi belirsiz değerlere sahip:  
  
```cpp  
int int_arr[3];  
```  
  
 Dizi üyeleri varsayılan bir oluşturucuya sahip değilse, derleyici bir hata gösterir.  
  
#### <a name="default-initialization-of-constant-variables"></a>Sabit değişkenlerin varsayılan başlatması  
 Sabit değişkenlerin bir başlatıcı ile birlikte bildirilmesi gerekir. Skaler türler olmaları durumunda, bunlar bir derleyici hatasına neden ve bunlar bir varsayılan oluşturucuya sahip sınıf türleriyse bir uyarıya neden olurlar:  
  
```cpp  
class MyClass{};  
int main() {  
    //const int i2;   // compiler error C2734: const object must be initialized if not extern  
    //const char c2;  // same error  
    const MyClass mc1; // compiler error C4269: 'const automatic data initialized with compiler generated default constructor produces unreliable results  
}  
```  
  
#### <a name="default-initialization-of-static-variables"></a>Statik değişkenlerin varsayılan başlatması  
 Başlatıcı ile bildirilen statik değişkenler 0 (örtük olarak türe dönüştürülür) başlatılır.  
  
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
  
 Genel statik nesnelerin başlatılması hakkında daha fazla bilgi için bkz: [ek başlatma konuları](../cpp/additional-startup-considerations.md).  
  
### <a name="value-initialization"></a>Değer başlatma  
 Değer başlatma aşağıdaki durumlarda oluşur:  
  
-   Adlandırılmış değer boş ayraç başlatma kullanılarak başlatılır.  
  
-   Anonim bir geçici nesne boş ayraçlar veya küme ayraçları kullanılarak başlatılır  
  
-   bir nesne ile başlatılır **yeni** anahtar sözcüğünün yanında boş ayraçlar veya küme ayraçları  
  
 Değer başlatma şunu yapar:  
  
-   en az bir ortak oluşturucuya sahip sınıflar için varsayılan oluşturucu çağrılır  
  
-   hiçbir bildirilen oluşturuculara sahip olmayan birliksiz sınıflar, nesne sıfır olarak başlatılır ve varsayılan oluşturucu çağrılır  
  
-   diziler için her öğe değer ile başlatılır  
  
-   Diğer durumlarda, değişken başlatılmamış sıfırdır  
  
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
  
### <a name="copy-initialization"></a>Kopya başlatma  
 Kopya başlatma, farklı bir nesne kullanarak bir nesnenin başlatmadır. Bunu, aşağıdaki durumlarda oluşur:  
  
-   bir değişken eşittir işareti kullanılarak başlatılır.  
  
-   bir bağımsız değişken bir işleve geçirilir  
  
-   bir nesne bir işlevden döndürülür  
  
-   bir özel durum oluşturulur veya yakalanır  
  
-   Statik olmayan veri üyesi, eşittir işareti kullanılarak başlatılır  
  
-   sınıf, yapı ve birlik üyeleri toplama başlatması sırasında kopya başlatma tarafından başlatılır. Bkz: [toplama başlatma](#agginit) örnekler.  
  
 Aşağıdaki kod, birden fazla kopya başlatma örneklerini gösterir:  
  
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
 Doğrudan başlatma (boş olmayan) küme ayraçları veya ayraçlar kullanarak başlatma işlemi. Kopya başlatmanın aksine açık oluşturucuları çağırabilir: Bunu, aşağıdaki durumlarda oluşur:  
  
-   bir değişken boş olmayan küme ayraçları veya ayraçlar ile başlatılır.  
  
-   bir değişken ile başlatılır **yeni** anahtar sözcüğünün yanında boş olmayan küme ayraçları veya ayraçlar  
  
-   bir değişken ile başlatılır **static_cast**  
  
-   bir oluşturucuda, temel sınıflar ve statik olmayan üyeler bir başlatıcı listesiyle başlatılır  
  
-   bir lambda ifadesi içinde yakalanan bir değişkenin kopyalama  
  
 Aşağıdaki kod, bazı doğrudan başlatma örneklerini gösterir:  
  
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
 Bir değişken bir küme ayracıyla belirtilen başlatıcı listesi kullanılarak başlatıldığında liste başlatma gerçekleşir. Küme ayracıyla belirtilen Başlatıcı Listeleri aşağıdaki durumlarda kullanılabilir:  
  
-   bir değişken başlatılır  
  
-   bir sınıf ile başlatılır **yeni** anahtar sözcüğü  
  
-   bir nesne bir işlevden döndürülür  
  
-   bir işleve geçirilen bağımsız değişken  
  
-   doğrudan başlatmadaki bağımsız değişkenlerden biri  
  
-   bir statik olmayan veri üyesi başlatıcıları  
  
-   bir oluşturucu başlatıcı listesinde  
  
 Aşağıdaki kod, bazı liste başlatma örneklerini gösterir:  
  
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
  
### <a name="agginit"></a> Toplama başlatma  
 Toplama başlatma diziler veya sınıf türleri için (çoğunlukla yapılar veya birlikler) şunlara sahip olan bir liste başlatma biçimidir:  
  
-   hiçbir özel veya korumalı üyeler  
  
-   açıkça varsayılan yapılmış veya silinmiş oluşturucular dışında hiçbir kullanıcı tarafından sağlanan oluşturucular  
  
-   temel olmayan sınıflar  
  
-   sanal üye işlev yok  
  
> [!NOTE]
>  <!--conformance note-->Visual Studio 2015 ve önceki sürümlerinde, bir toplama statik olmayan üyeler için küme ayracı-veya-eşittir Başlatıcısı için izin verilmiyor. Bu kısıtlama C ++ 14 standartı'kaldırıldı ve Visual Studio 2017'de uygulanır. 
  
 Toplama başlatıcıları ile veya aşağıdaki örnekteki gibi bir eşittir işareti olmadan bir küme ayracıyla belirtilen başlatma listesinden oluşur:  
  
```cpp  
#include <iostream>  
using namespace std;  
  
struct MyAggregate{  
    int myInt;  
    char myChar;  
};  
  
int main() {  
    MyAggregate agg1{ 1, 'c' };  
  
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
  
```  
agg1: c: 1  
agg2: d: 2  
myArr1: 1 2 3 4  
myArr3: 8 9 10 0 0  
```  
  
> [!IMPORTANT]
>  Bildirilmiş ancak toplama başlatma sırasında açıkça başlatılan dizi üyeleri sıfır başlatılır olarak `myArr3` yukarıda.  
  
#### <a name="initializing-unions-and-structs"></a>Birleşimleri ve yapıları başlatma  
 Bir birleşimin bir oluşturucu yoksa, tek bir değer (veya başka bir örneği bir birleşim ile) başlatabilirsiniz. Değer, ilk statik olmayan alanı başlatmak için kullanılır. Bu, içinde ilk alanı başlatmak için kullanılan ilk değerin, ikinci alanı başlatmak için ikincinin vb. bulunduğu yapı başlatmadan farklıdır. Başlatma birleşimlerin ve yapıların aşağıdaki örnekte karşılaştırın:  
  
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
  
#### <a name="initializing-aggregates-that-contain-aggregates"></a>Toplamları içeren toplamaları başlatma  
 Toplama türleri diğer toplama türleri, örneğin dizilerin dizileri, dizi yapılar vb. içerebilir. Bu tür, örneğin, ayraçlarının iç içe kümeleri kullanarak başlatılır:  
  
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
 Başvuru türü değişkenler, bir nesnenin bir başvuru türü türetilen türünü veya başvuru türü türetildiği türüne dönüştürülebilen bir türde bir nesne ile başlatılmalıdır. Örneğin:  
  
```  
// initializing_references.cppint   
int iVar;  
long lVar;  
int main()   
{   long& LongRef1 = lVar;   // No conversion required.  
   long& LongRef2 = iVar;   // C2440  
   const long& LongRef3 = iVar;   // OK  
   LongRef1 = 23L;   // Change lVar through a reference.  
   LongRef2 = 11L;   // Change iVar through a reference.  
   LongRef3 = 11L;   // C3892}  
```  
  
 Geçici bir nesne ile bir başvuruyu başlatmak üzere tek bir sabit geçici nesne başlatmak için yoludur. Başlatıldıktan sonra bir başvuru türü değişken her zaman aynı nesneye işaret eder; başka bir nesneye işaret edecek şekilde değiştirilemez.  
  
 Sözdizimi Başvuru türü değişkenlerin ve atama için aynı, başlatma olsa da, başvuru türü değişkenler anlamsal olarak farklı. Atamalar, önceki örnekte, değiştirme `iVar` ve `lVar` başlatmalar için benzer, ancak başka etkileri olabilir. Başlatma, başvuru türü değişkenin işaret ettiği nesnenin belirtir. başvurulan nesne başvurusu aracılığıyla atama atar.  
  
 Başvuru türünde bir bağımsız değişken bir işleve nasıl geçirileceğini hem başvuru türünde bir değer döndüren bir işlevden başlatmalar olduğundan, döndürülen başvuru olarak bir işlevin biçimsel bağımsız değişkenleri doğru başlatılır.  
  
 Başvuru türü değişkenler yalnızca içinde aşağıdaki başlatıcılar olmadan bildirilebilir:  
  
-   İşlev bildirimleri (prototipler). Örneğin:  
  
    ```  
    int func( int& );  
    ```  
  
-   İşlev dönüş türü bildirimleri. Örneğin:  
  
    ```  
    int& func( int& );  
    ```  
  
-   Bir başvuru türü sınıf üyesinin bildirimi. Örneğin:  
  
    ```  
    class c {public:   int& i;};  
    ```  
  
-   Açıkça belirtilen bir değişkenin bildirimi **extern**. Örneğin:  
  
    ```  
    extern int& iVal;  
    ```  
  
 Derleyici aşağıdaki şekilde gösterilen karar grafiği bir başvuru türü değişken başlatılırken bir nesneye bir başvuru veya başvurunun işaret ettiği geçici bir nesne oluşturarak arasında seçmek için kullanır.  
  
 ![Başvuru türlerinin başlatma için karar grafiği](../cpp/media/vc38s71.gif "vc38S71")  
Başvuru türlerinin başlatma için karar grafiği  
  
 Başvurular **geçici** türleri (olarak bildirilen **geçici** *typename *** &** *tanımlayıcı*) başlatılabilir ile **geçici** nesneleri aynı türde veya olarak bildirilmemiş nesnelerle **geçici**. Olamaz, ancak, ile başlatılması **const** nesnelerin türü. Benzer şekilde, başvurular **const** türleri (olarak bildirilen **const** *typename *** &** *tanımlayıcı*) olabilir ile başlatıldı **const** nesneleri aynı türdeki (veya bir dönüştürme türü veya nesnelerle olarak bildirilmemiş olan herhangi bir şeyi **const**). Olamaz, ancak, ile başlatılması **geçici** nesnelerin türü.  
  
 İle yetkili değil başvuruları **const** veya **geçici** anahtar sözcüğü, yalnızca hiçbiri bildirilen nesneler ile başlatılabilir **const** ya da  **volatile**.  
  
### <a name="initialization-of-external-variables"></a>Dış değişkenleri başlatma  
 Otomatik, statik ve dış değişkenler bildirimleri başlatıcılar içerebilir. Ancak, yalnızca değişkenleri olarak bildirilmedikçe dış değişkenlerin bildirimleri Başlatıcı içerebilir **extern**.
  
