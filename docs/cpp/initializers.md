---
title: "Başlatıcılar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- array-element initializers
- initializing arrays [C++], initializers
- arrays [C++], array-element initializers
- declarators, as initializers
- initializers, array element
ms.assetid: ce301ed8-aa1c-47b2-bb39-9f0541b4af85
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: be05c53e6f41c4df4d62bd4ba1920fcf57c1f0cb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
  
-   Char değişkenleri için başlatılır `'\0'`.  
  
-   İşaretçileri için başlatılır `nullptr`.  
  
-   Diziler, [POD](../standard-library/is-pod-class.md) sınıflar, yapılar ve birleşimleri sahip üyeleri için sıfır değeri başlatılmadı.  
  
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
  
### <a name="default_initialization"></a>Varsayılan başlatma  
 Varsayılan başlatma sınıflar, yapılar ve birleşimleri için varsayılan bir Oluşturucu ile başlatma işlemi. Varsayılan oluşturucu veya hiçbir başlatma ifade ile çağrılabilir `new` anahtar sözcüğü:  
  
```cpp  
MyClass mc1;  
MyClass* mc3 = new MyClass;  
```  
  
 Sınıf, yapı veya birleşim varsayılan oluşturucuya sahip değilse, derleyici bir hata gösterir.  
  
 Hiçbir başlatma ifadesiyle tanımlandığında başlatılmış varsayılan skaler değişkenlerdir. Belirsiz değerlere sahiptirler.  
  
```cpp  
int i1;  
float f;  
char c;  
```  
  
 Hiçbir başlatma ifadesiyle tanımlandığında başlatılmış varsayılan dizidir. Bir dizi varsayılan başlatılmış olduğunda, üyelerine varsayılan başlatıldı ve aşağıdaki örnekteki gibi belirsiz değerlere sahip:  
  
```cpp  
int int_arr[3];  
```  
  
 Dizi üyeleri varsayılan bir oluşturucuya sahip değilse, derleyici bir hata gösterir.  
  
#### <a name="default-initialization-of-constant-variables"></a>Sabit değişkenlerin varsayılan başlatma  
 Sabit değişkenlerin bir başlatıcı ile birlikte bildirilmesi gerekir. Skaler türler varsa bunlar derleyici hatası neden ve varsayılan bir oluşturucuya sahip sınıf türleri olmaları durumunda bir uyarı neden:  
  
```cpp  
class MyClass{};  
int main() {  
    //const int i2;   // compiler error C2734: const object must be initialized if not extern  
    //const char c2;  // same error  
    const MyClass mc1; // compiler error C4269: 'const automatic data initialized with compiler generated default constructor produces unreliable results  
}  
```  
  
#### <a name="default-initialization-of-static-variables"></a>Statik değişkenler varsayılan olarak başlatılması  
 Hiçbir Başlatıcı ile bildirilen statik değişkenler, 0 (örtük olarak türe dönüştürülüp) başlatılır.  
  
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
 Değer başlatma aşağıdaki durumlarda gerçekleşir:  
  
-   adlandırılmış bir değer boş ayraç başlatma kullanarak başlatılır  
  
-   boş ayraç veya küme ayraçları kullanarak geçici bir anonim nesnenin başlatıldı  
  
-   bir nesne ile başlatılmış `new` anahtar sözcüğü artı boş ayraç veya küme ayraçları  
  
 Değer başlatma şunları yapar:  
  
-   en az bir ortak Oluşturucu ile sınıflar için varsayılan oluşturucu çağrılır  
  
-   bildirilen oluşturucu yok ile olmayan birleşim sınıfları, sıfır başlatılmış nesnedir ve varsayılan oluşturucu çağrılır  
  
-   diziler için her öğenin değeri başlatıldı  
  
-   Diğer durumlarda, değişkeni başlatılmış sıfırdır  
  
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
 Kopya başlatma farklı bir nesne kullanarak bir nesnenin başlatma işlemi. Aşağıdaki durumlarda gerçekleşir:  
  
-   bir değişkeni bir eşittir işareti kullanılarak başlatılır  
  
-   bir işleve bağımsız değişken geçirildi  
  
-   bir nesne bir işleve döndürülür  
  
-   bir özel durum ya da yakalandı  
  
-   Statik olmayan veri üyesi bir eşittir işareti kullanılarak başlatılır  
  
-   sınıf, yapı ve birleşim üyeleri kopyalama başlatma toplu başlatma sırasında tarafından başlatılır. Bkz: [toplu başlatma](#agginit) örnekleri için.  
  
 Aşağıdaki kod kopyalama başlatma bazı örnekleri gösterir:  
  
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
  
 Kopya başlatma açık oluşturucular çağıramaz.  
  
```cpp  
vector<int> v = 10; // the constructor is explicit; compiler error C2440: cannot convert from 'int' to 'std::vector<int,std::allocator<_Ty>>'  
regex r = "a.*b"; // the constructor is explicit; same error  
shared_ptr<int> sp = new int(1729); // the constructor is explicit; same error  
```  
  
 Bazı durumlarda, sınıfın kopya oluşturucusu silinmişse veya erişilemezse, kopya başlatma bir derleyici hatasına neden olur. 
  
### <a name="direct-initialization"></a>Doğrudan başlatma  
 Doğrudan başlatma (boş) kuşak ya da parantez kullanarak başlatma işlemi. Kopya başlatmanın aksine açık oluşturucuları çağırabilir: Aşağıdaki durumlarda gerçekleşir:  
  
-   bir değişkeni boş olmayan küme ayraçları veya parantez ile başlatıldı  
  
-   bir değişken ile başlatılmış `new` anahtar sözcüğü artı boş olmayan küme ayraçları veya parantez  
  
-   bir değişken ile başlatıldı`static_cast`  
  
-   bir oluşturucu başlatıcı listesi ile temel sınıflar ve statik olmayan üye başlatılır  
  
-   lambda ifadesi içinde yakalanan bir değişkenin kopyalama  
  
 Aşağıdaki kod doğrudan başlatma bazı örnekler gösterilmektedir:  
  
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
 Bir küme ayracı içine alınan başlatıcı listesi kullanarak bir değişken başlatıldığında listesi başlatma gerçekleşir. Başlatıcı Listeleri aşağıdaki durumlarda kullanılabilir braced:  
  
-   bir değişkeni başlatılır  
  
-   bir sınıf ile başlatılmış `new` anahtar sözcüğü  
  
-   bir nesne bir işleve döndürülür  
  
-   bir işleve bağımsız değişken  
  
-   bir doğrudan başlatma bağımsız değişkenler  
  
-   bir statik olmayan veri üyesi Başlatıcı  
  
-   oluşturucu başlatıcı listesinde  
  
 Aşağıdaki kod listesi başlatma bazı örnekler gösterilmektedir:  
  
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
  
-   hiçbir özel veya korumalı üyeler  
  
-   açıkça varsayılan veya silinen oluşturucular dışında hiçbir kullanıcı tarafından sağlanan oluşturucular  
  
-   Hiçbir temel sınıflar  
  
-   hiçbir sanal üye işlevleri  
  
> [!NOTE]
>  <!--conformance note-->In Visual Studio 2015 and earlier, an aggregate is not allowed to have  brace-or-equal initializers for non-static members. This restriction was removed in the C++14 standard and implemented in Visual Studio 2017. 
  
 Küme ayracı içine alınan başlatma listesi ile veya aşağıdaki örnekteki gibi bir eşittir işareti olmadan toplama başlatıcıları oluşur:  
  
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
  
 Şu çıktı görmeniz gerekir:  
  
```  
agg1: c: 1  
agg2: d: 2  
myArr1: 1 2 3 4  
myArr3: 8 9 10 0 0  
```  
  
> [!IMPORTANT]
>  Bildirilen, ancak açıkça toplu başlatma sırasında başlatılan dizi üyeleri sıfır-başlatıldı, olarak `myArr3` üstünde.  
  
#### <a name="initializing-unions-and-structs"></a>Birleşimler ve yapıları başlatma  
 UNION bir oluşturucuya sahip değil, tek bir değer (veya başka bir örneği bir birleşimi) başlatabilirsiniz. Değer, ilk statik olmayan alanı başlatmak için kullanılır. Bu, içinde ilk alanı başlatmak için kullanılan ilk değerin, ikinci alanı başlatmak için ikincinin vb. bulunduğu yapı başlatmadan farklıdır. Birleşimler ve aşağıdaki örnekte yapılar başlatılması karşılaştırın:  
  
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
  
#### <a name="initializing-aggregates-that-contain-aggregates"></a>Toplamalar içeren toplamalar başlatılıyor  
 Toplama türleri diziler, yapılar ve benzeri bir dizi örnek dizileri için diğer toplama türleri içerebilir. Bu tür, örneğin küme ayraçları iç içe geçmiş kümelerini kullanarak başlatılır:  
  
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
 Başvuru türündeki değişkenler başvuru türü türetilen gelen türünde bir nesne veya başvuru türü türetildiği türüne dönüştürülebilir türünde bir nesne ile başlatılması gerekir. Örneğin:  
  
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
  
 Bir başvuru geçici bir nesne ile başlatmak için yalnızca sabit bir geçici nesneyi başlatmak için yoludur. Başlatıldıktan sonra bir başvuru türü değişken her zaman aynı nesneye işaret eder; başka bir nesneye işaret edecek şekilde değiştirilemez.  
  
 Başvuru türü değişkenleri sözdizimi başvuru türü değişkenlerin ve atama için aynı, başlatma olsa da semantik olarak farklıdır. Önceki örnekte atamaları, değiştirme `iVar` ve `lVar` başlatmaları benzer, ancak başka etkileri olabilir. Başlatma başvuru türü değişkenin işaret ettiği nesnesini belirtir; başvuru aracılığıyla başvurulan nesneye atama atar.  
  
 Başvuru türünde bir bağımsız değişken bir işleve geçirme hem başvuru türünde bir değer döndüren bir işleve başlatmaları olduğundan, döndürülen başvuruları gibi bir çalışması biçimsel bağımsız değişkenler, doğru başlatılır.  
  
 Başvuru türü değişkenleri aşağıdaki içinde yalnızca başlatıcılar olmadan bildirilebilir:  
  
-   İşlev bildirimleri (prototipleri). Örneğin:  
  
    ```  
    int func( int& );  
    ```  
  
-   İşlev dönüş türü bildirimi. Örneğin:  
  
    ```  
    int& func( int& );  
    ```  
  
-   Başvuru türü sınıf üyesi bildirim. Örneğin:  
  
    ```  
    class c {public:   int& i;};  
    ```  
  
-   Olarak açıkça belirtilen bir değişken bildirimi `extern`. Örneğin:  
  
    ```  
    extern int& iVal;  
    ```  
  
 Bir başvuru türü değişkenini başlatırken derleyici bir nesneye başvuru veya reference işaret ettiği geçici bir nesne oluşturarak arasında seçmek için aşağıdaki resimde gösterilen karar grafiği kullanır.  
  
 ![Ref türleri başlatma için karar grafiği](../cpp/media/vc38s71.gif "vc38S71")  
Başvuru türleri başlatma için karar grafiği  
  
 Başvurular `volatile` türleri (olarak bildirilen `volatile` *typename*  **&**  *tanımlayıcısı*) ile başlatılmış `volatile` nesneleri aynı türde veya olarak bildirilmemiş nesnelerle `volatile`. Olamaz, ancak, ile başlatılması **const** bu tür nesneleri. Benzer şekilde, başvurular **const** türleri (olarak bildirilen **const** *typename*  **&**  *tanımlayıcısı* ) ile başlatılmış **const** aynı türde nesneler (veya bir dönüştürme türü veya olarak bildirilmemiş nesnelerle sahip herhangi bir şeyi **const**). Olamaz, ancak, ile başlatılması `volatile` bu tür nesneleri.  
  
 İle ya da nitelikli'ları değil başvuruları **const** veya `volatile` anahtar sözcüğü yalnızca hiçbiri bildirilen nesnelerle başlatılabilir **const** ya da `volatile`.  
  
### <a name="initialization-of-external-variables"></a>Dış değişkenleri başlatma  
 Otomatik, statik ve dış değişkenleri bildirimlerini başlatıcıları içerebilir. Ancak, yalnızca değişkenleri olarak bildirilmeyen seçerseniz dış değişken bildirimleri başlatıcıları içerebilir `extern`.
  
