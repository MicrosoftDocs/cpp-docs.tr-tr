---
title: "Oluşturucular (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- constructors [C++]
- objects [C++], creating
- instance constructors
ms.assetid: 3e9f7211-313a-4a92-9584-337452e061a9
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 77007b3d3805bb2fa159680c88d8e41825336da2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="constructors-c"></a>Oluşturucular (C++)
Bir oluşturucu, kendi sınıfının bir örneğini başlatır üye işlevi türüdür. Bir oluşturucu sınıf ve hiçbir değer döndürmeyen aynı ada sahip. Bir Oluşturucu parametreleri herhangi bir sayıda olabilir ve bir sınıf herhangi bir sayıda aşırı yüklü oluşturucular olabilir. Oluşturucular herhangi erişilebilirlik, genel, korumalı veya özel olabilir. Tüm oluşturucuları tanımlama yok derleyici parametre almayan varsayılan bir oluşturucu oluşturur; silinmiş olarak varsayılan bir oluşturucu bildirerek bu davranışı geçersiz kılabilirsiniz.  
  
## <a name="in-this-topic"></a>Bu konuda  
  
-   [Yapı sırası](#order_of_construction)  
  
-   [Üye listeleri](#member_lists)  
  
-   [Açıkça oluşturucular](#explicit_constructors)  
  
-   [Varsayılan Oluşturucu](#default_constructors)  
  
-   [Kopyalama ve taşıma oluşturucuları](#copy_and_move_constructors)  
  
-   [Açıkça varsayılan haline getirilen ve Silinen oluşturucular](#explicitly_defaulted_and_deleted_constructors)  
  
-   [Türetilmiş sınıflarda oluşturucular](#constructors_in_derived_classes)  
  
-   [Oluşturucular içinde sanal işlevleri](#virtual_functions_in_constructors)  
  
-   [Oluşturucular ve bileşik sınıfları](#constructors_in_composite_classes)  
  
-   [Oluşturucular için temsilci seçme](#delegating_constructors)  
  
-   [Oluşturucular (C ++ 11) devralma](#inheriting_constructors)  
  
-   [Oluşturucuları bildirme kuralları](#rules_for_declaring_constructors)  
  
-   [Açıkça oluşturucular çağırma](#explicitly_invoking_constructors)  
  
##  <a name="order_of_construction"></a>Yapı sırası  
 Bir oluşturucu kendi işini şu sırayla gerçekleştirir:  
  
1.  Temel sınıfı ve üye oluşturucuları bildirim sırasına göre çağırır.  
  
2.  Sınıf sanal temel sınıflardan türetilmişse, nesnenin sanal taban işaretçilerini başlatır.  
  
3.  Sınıf sanal işlevler içeriyorsa ya da devralıyorsa, nesnenin sanal işlev işaretçilerini başlatır. Sanal işlev işaretçileri, sanal işlev çağrılarının koda doğru bağlanmasını sağlamak için sınıfın sanal işlev tablosunu gösterir.  
  
4.  Kendi işlev gövdesindeki tüm kodları yürütür.  
  
 Aşağıdaki örnek, türetilmiş bir sınıfın oluşturucusundaki temel sınıfın ve üye oluşturucuların çağrılma sırasını göstermektedir. Önce taban oluşturucu çağrılır, sonra taban sınıfı üyeleri sınıf bildiriminde görüldükleri sırayla başlatılır ve ardından türetilen oluşturucu çağrılır.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
class Contained1 {  
public:  
    Contained1() {  
        cout << "Contained1 constructor." << endl;  
    }  
};  
  
class Contained2 {  
public:  
    Contained2() {  
        cout << "Contained2 constructor." << endl;  
    }  
};  
  
class Contained3 {  
public:  
    Contained3() {  
        cout << "Contained3 constructor." << endl;  
    }  
};  
  
class BaseContainer {  
public:  
    BaseContainer() {  
        cout << "BaseContainer constructor." << endl;  
    }  
private:  
    Contained1 c1;  
    Contained2 c2;  
};  
  
class DerivedContainer : public BaseContainer {  
public:  
    DerivedContainer() : BaseContainer() {  
        cout << "DerivedContainer constructor." << endl;  
    }  
private:  
    Contained3 c3;  
};  
  
int main() {  
    DerivedContainer dc;  
    int x = 3;  
}  
  
```  
  
 Çıkış şu şekildedir:  
  
```  
Contained1 constructor.  
Contained2 constructor.  
BaseContainer constructor.  
Contained3 constructor.  
DerivedContainer constructor.  
```  
  
 Bir oluşturucu özel bir durum oluşturursa, yok etme sırası oluşturma sırasının tersidir:  
  
1.  Oluşturucu işlevinin gövdesindeki kod geriye doğru çözülür.  
  
2.  Temel sınıf ve üye nesneleri bildirimin tersi sırada yok edilir.  
  
3.  Oluşturucu temsil eden değilse, tam oluşturulmuş tüm taban sınıfı nesneleri ve üyeleri yok edilir. Ancak nesnenin kendisi tam oluşturulmadığından yok edici çalışmaz.  
  
##  <a name="member_lists"></a>Üye listeleri  
 Sınıf üyeleri oluşturucu bağımsız değişkenleri bir üye başlatıcı listesi kullanılarak başlatır. Bu yöntem *doğrudan başlatma*, atama işleçleri Oluşturucusu gövdesi içinde kullanmaktan daha verimli olduğu.  
  
```cpp  
class Box {  
public:  
    Box(int width, int length, int height)   
        : m_width(width), m_length(length), m_height(height) // member init list  
    {}  
    int Volume() {return m_width * m_length * m_height; }  
private:  
    int m_width;  
    int m_length;  
    int m_height;  
  
};  
  
```  
  
 Kutusunu nesnesi oluşturun:  
  
```  
Box b(42, 21, 12);  
cout << "The volume is " << b.Volume();  
```  
  
##  <a name="explicit_constructors"></a>Açıkça oluşturucular  
 Bir sınıfın tek bir parametre ile bir oluşturucu varsa veya biri dışındaki tüm parametreler varsayılan bir değer varsa, parametre türü örtük olarak sınıfı türüne dönüştürülebilir. Örneğin, varsa `Box` sınıfı şöyle bir oluşturucu sahiptir:  
  
```  
Box(int size): m_width(size), m_length(size), m_height(size){}  
```  
  
 Böyle bir kutusunu başlatma mümkündür:  
  
```  
Box b = 42;  
```  
  
 Veya bir kutusu götüren bir işleve int geçirebilirsiniz:  
  
```  
class ShippingOrder  
{  
public:  
    ShippingOrder(Box b, double postage) : m_box(b), m_postage(postage){}  
  
private:  
    Box m_box;  
    double m_postage;  
}  
//elsewhere...  
    ShippingOrder so(42, 10.8);  
  
```  
  
 Bu tür dönüşümleri bazı durumlarda yararlı olabilir, ancak daha sık Zarif ancak ciddi hatalar, kodunuzda açabilir. Genel kural olarak, kullanması gereken `explicit` anahtar sözcüğü bu tür bir örtük tür dönüştürmesi önlemek için bir oluşturucu (ve kullanıcı tanımlı işleçler):  
  
```  
  
explicit Box(int size): m_width(size), m_length(size), m_height(size){}  
```  
  
 Oluşturucusu açık olduğunda, bu satırın derleyici hatası neden olur: `ShippingOrder so(42, 10.8);`.  Daha fazla bilgi için bkz: [kullanıcı tanımlı tür dönüşümleri](../cpp/user-defined-type-conversions-cpp.md).  
  
##  <a name="default_constructors"></a>Varsayılan Oluşturucu  
 *Varsayılan oluşturucular* ; parametresi olmayan biraz farklı kuralları izleyin:  
  
 Varsayılan Oluşturucu biri olan *özel üye işlevleri*; oluşturucu yok bir sınıf içinde bildirilen derleyici varsayılan bir oluşturucu sağlar:  
  
```cpp  
class Box {  
    Box(int width, int length, int height)   
        : m_width(width), m_length(length), m_height(height){}  
};  
  
int main(){  
  
    Box box1{}; // call compiler-generated default ctor  
    Box box2;   // call compiler-generated default ctor  
}  
```  
  
 Varsayılan bir oluşturucuyu çağırdığınızda ve parantez kullanmaya çalıştığınızda, bir uyarı verilir:  
  
```cpp  
class myclass{};  
int main(){  
myclass mc();     // warning C4930: prototyped function not called (was a variable definition intended?)  
}  
```  
  
 Bu, En Çok Güçlük Çıkaran Ayrıştırma sorununa bir örnektir. Örnek ifade bir işlevin bildirimi ya da varsayılan bir oluşturucunun çağrılması olarak yorumlanabileceğinden ve C++ ayrıştırıcıları diğer şeylere oranla bildirimlere öncelik verdiğinden, ifade bir işlev bildirimi olarak ele alınır. Daha fazla bilgi için bkz: [en Vexing ayrıştırma](http://en.wikipedia.org/wiki/Most_vexing_parse).  
  
 Varsayılan olmayan bir oluşturucu bildirilirse, derleyici varsayılan bir oluşturucu sağlamaz:  
  
```cpp  
class Box {  
    Box(int width, int length, int height)   
        : m_width(width), m_length(length), m_height(height){}  
};  
private:  
    int m_width;  
    int m_length;  
    int m_height;  
  
};  
  
int main(){  
  
    Box box1(1, 2, 3);  
    Box box2{ 2, 3, 4 };  
    Box box4;     // compiler error C2512: no appropriate default constructor available  
}  
  
```  
  
 Bir sınıfın varsayılan oluşturucusu yoksa, o sınıfa ait nesneler dizisi yalnızca köşeli paranteze sahip bir sözdizimi kullanılarak oluşturulamaz. Örneğin önceki kod bloğu düşünüldüğünde, bir Kutular dizisi şu şekilde bildirilemez:  
  
```cpp  
Box boxes[3];    // compiler error C2512: no appropriate default constructor available  
  
```  
  
 Ancak, bir Kutular dizisi başlatmak için başlatıcı listelerinin bir kümesini kullanabilirsiniz:  
  
```cpp  
Box boxes[3]{ { 1, 2, 3 }, { 4, 5, 6 }, { 7, 8, 9 } };  
```  
  
##  <a name="copy_and_move_constructors"></a>Kopyalama ve taşıma oluşturucuları  
 A *kopya Oluşturucu* aynı nesneye bir başvurusu yazın ve bir kopyasını oluşturur girdi olarak alır özel üye işlevdir. Daha fazla bilgi için bkz: [kopya oluşturucuları ve kopya atama işleçleri (C++)](../cpp/copy-constructors-and-copy-assignment-operators-cpp.md). A *taşıma Oluşturucusu* da özgün veri kopyalama olmadan yeni bir değişken mevcut nesnenin verileri sahipliğini taşınan bir özel üye işlevdir. Daha fazla bilgi için bkz: [taşıma oluşturucuları ve taşıma atama işleçleri (C++)](../cpp/move-constructors-and-move-assignment-operators-cpp.md).  
  
##  <a name="explicitly_defaulted_and_deleted_constructors"></a>Açıkça varsayılan haline getirilen ve Silinen oluşturucular  
 Açıkça yapabilecekleriniz *varsayılan* kopyalama Oluşturucular, varsayılan Oluşturucular, Oluşturucular taşımak, atama işleçleri kopyalayın, Yıkıcılar getirip atama işleçleri. Açıkça yapabilecekleriniz *silmek* tüm özel üye işlevleri. Daha fazla bilgi için bkz: [açıkça varsayılan ve Silinen işlevler](../cpp/explicitly-defaulted-and-deleted-functions.md).  
  
##  <a name="constructors_in_derived_classes"></a>Türetilmiş sınıflarda oluşturucular  
 Bir türetilmiş sınıf oluşturucusu her zaman bir taban sınıf oluşturucusunu çağırır, böylece bu sınıf ek bir çalışma yapılmadan önce tümüyle oluşturulmuş taban sınıflarına dayanabilir. Temel sınıf oluşturucuları türetilme sıralarına göre çağrılır; örneğin SınıfA SınıfB'den, o ise SınıfC'den türetilmişse, önce SınıfC oluşturucusu, ardından SınıfB oluşturucusu, ardından da SınıfA oluşturucusu çağrılır.  
  
 Bir taban sınıfında varsayılan bir oluşturucu yoksa, türetilen sınıf oluşturucusu içinde temel sınıf oluşturucu parametresini sağlamalısınız:  
  
```cpp  
class Box {  
public:  
    Box(int width, int length, int height){  
       m_width = width;  
       m_length = length;  
       m_height = height;  
    }  
  
private:  
    int m_width;  
    int m_length;  
    int m_height;  
};  
  
class StorageBox : public Box {  
public:  
    StorageBox(int width, int length, int height, const string label&) : Box(width, length, height){  
        m_label = label;  
    }  
private:  
    string m_label;  
};  
  
int main(){  
  
    const string aLabel = "aLabel";  
    StorageBox sb(1, 2, 3, aLabel);  
}   
```  
  
### <a name="constructors-for-classes-that-have-multiple-inheritance"></a>Birden Çok Kalıtıma Sahip Sınıfların Oluşturucuları  
 Bir sınıf birden çok temel sınıftan türetiliyorsa, temel sınıf oluşturucuları türetilen sınıfın bildirimi içinde listelendikleri sırayla çağrılır:  
  
```cpp  
#include <iostream>  
using namespace std;  
  
class BaseClass1 {  
public:  
    BaseClass1() {  
        cout << "BaseClass1 constructor." << endl;  
    }  
};  
class BaseClass2 {  
public:  
    BaseClass2() {  
        cout << "BaseClass2 constructor." << endl;  
    }  
};  
class BaseClass3{  
public:  
    BaseClass3() {  
        cout << "BaseClass3 constructor." << endl;  
    }  
};  
class DerivedClass : public BaseClass1, public BaseClass2, public BaseClass3  {  
public:  
    DerivedClass() {  
        cout << "DerivedClass constructor." << endl;  
    }  
};  
  
int main() {  
    DerivedClass dc;  
}  
  
```  
  
 Aşağıdaki çıktıyı beklemelisiniz:  
  
```  
BaseClass1 constructor.  
BaseClass2 constructor.  
BaseClass3 constructor.  
DerivedClass constructor.  
```  
  
##  <a name="virtual_functions_in_constructors"></a>Oluşturucular içinde sanal işlevleri  
 Oluşturucularda sanal işlevleri çağırırken dikkatli olmanız önerilir. Temel sınıf oluşturucusu her zaman türetilen sınıf oluşturucusundan önce çağrıldığından, temel oluşturucu içinde çağrılan işlev türetilen sınıf sürümü değil, temel sınıf sürümüdür. Aşağıdaki örnekte, oluşturma bir `DerivedClass` neden `BaseClass` uyarlamasını `print_it()` önce yürütülecek `DerivedClass` Oluşturucusu nedenler `DerivedClass` uyarlamasını `print_it()` yürütmek için:  
  
```cpp  
#include <iostream>  
using namespace std;  
  
class BaseClass{  
public:  
    BaseClass(){  
        print_it();  
    }  
    virtual void print_it() {  
        cout << "BaseClass print_it" << endl;  
    }  
};  
  
class DerivedClass : public BaseClass {  
public:  
    DerivedClass() {  
        print_it();  
    }  
    virtual void print_it(){  
        cout << "Derived Class print_it" << endl;  
    }  
};  
  
int main() {  
  
    DerivedClass dc;  
}  
```  
  
 Çıkış şu şekildedir:  
  
```  
BaseClass print_it  
Derived Class print_it  
```  
  
##  <a name="constructors_in_composite_classes"></a>Oluşturucular ve bileşik sınıfları  
 Sınıf türü üyeleri içeren sınıflar olarak bilinen *bileşik sınıfları*. Bileşik bir sınıfın sınıf türünde bir üyesi oluşturulduğunda, sınıfın kendisi çağrılmadan önce oluşturucu çağrılır. İçerilen bir sınıfın varsayılan bir oluşturucusu yoksa, bileşik sınıfın oluşturucusunda bir başlatma listesi kullanmalısınız. Önceki içinde `StorageBox` türünü değiştirirseniz, örnek `m_label` yeni bir üye değişkenine `Label` sınıfı, temel sınıf kurucusunu çağırmak ve gerekir başlatma `m_label` değişkeni `StorageBox` Oluşturucusu:  
  
```cpp  
class Label {  
public:  
    Label(const string& name, const string& address) { m_name = name; m_address = address; }  
    string m_name;  
    string m_address;  
};  
  
class StorageBox : public Box {  
public:  
    StorageBox(int width, int length, int height, Label label)   
        : Box(width, length, height), m_label(label){}  
private:  
    Label m_label;  
};  
  
int main(){  
// passing a named Label  
    Label label1{ "some_name", "some_address" };  
    StorageBox sb1(1, 2, 3, label1);  
  
    // passing a temporary label  
    StorageBox sb2(3, 4, 5, Label{ "another name", "another address" });  
  
    // passing a temporary label as an initializer list  
    StorageBox sb3(1, 2, 3, {"myname", "myaddress"});  
}  
```  
  
##  <a name="delegating_constructors"></a>Oluşturucular için temsilci seçme  
 A *oluşturucusu için temsilci seçme* farklı bir oluşturucu başlatma işinin bir kısmını yapmak için aynı sınıfta çağırır. Aşağıdaki örnekte, türetilen sınıfın üç oluşturucusu vardır; ikinci oluşturucu birinciyi ve üçüncü oluşturucu ikinciyi temsil eder:  
  
```cpp  
#include <iostream>  
using namespace std;  
  
class ConstructorDestructor {  
public:  
    ConstructorDestructor() {  
        cout << "ConstructorDestructor default constructor." << endl;  
    }  
    ConstructorDestructor(int int1) {  
        cout << "ConstructorDestructor constructor with 1 int." << endl;  
    }  
    ConstructorDestructor(int int1, int int2) : ConstructorDestructor(int1) {  
        cout << "ConstructorDestructor constructor with 2 ints." << endl;  
  
        throw exception();  
    }  
    ConstructorDestructor(int int1, int int2, int int3) : ConstructorDestructor(int1, int2) {  
        cout << "ConstructorDestructor constructor with 3 ints." << endl;  
    }  
    ~ConstructorDestructor() {  
        cout << "ConstructorDestructor destructor." << endl;  
    }  
};  
  
int main() {  
    ConstructorDestructor dc(1, 2, 3);  
}  
  
```  
  
 Çıkış şu şekildedir:  
  
```  
ConstructorDestructor constructor with 1 int.  
ConstructorDestructor constructor with 2 ints.  
ConstructorDestructor constructor with 3 ints.  
```  
  
 Herhangi bir oluşturucunun işi biter bitmez, oluşturucular tarafından oluşturulan nesne tamamen başlatılır. `DerivedContainer(int int1)`başarılı, ancak `DerivedContainer(int int1, int int2)` başarısız olur ve yıkıcı çağrılır.  
  
```cpp  
class ConstructorDestructor {  
public:  
    ConstructorDestructor() {  
        cout << "ConstructorDestructor default constructor." << endl;  
    }  
    ConstructorDestructor(int int1) {  
        cout << "ConstructorDestructor constructor with 1 int." << endl;  
    }  
    ConstructorDestructor(int int1, int int2) : ConstructorDestructor(int1) {  
        cout << "ConstructorDestructor constructor with 2 ints." << endl;  
        throw exception();  
    }  
    ConstructorDestructor(int int1, int int2, int int3) : ConstructorDestructor(int1, int2) {  
        cout << "ConstructorDestructor constructor with 3 ints." << endl;  
    }  
  
    ~ConstructorDestructor() {  
        cout << "ConstructorDestructor destructor." << endl;  
    }  
};  
  
int main() {  
  
    try {  
        ConstructorDestructor cd{ 1, 2, 3 };  
    }  
    catch (const exception& ex){  
    }  
}  
  
```  
  
 Çıktı:  
  
```  
ConstructorDestructor constructor with 1 int.  
ConstructorDestructor constructor with 2 ints.  
ConstructorDestructor destructor.  
```  
  
 Daha fazla bilgi için bkz: [tek düzen başlatma ve oluşturucuları temsilci](../cpp/uniform-initialization-and-delegating-constructors.md).  
  
##  <a name="inheriting_constructors"></a>Oluşturucular (C ++ 11) devralma  
 Türetilmiş bir sınıf oluşturucular doğrudan bir taban sınıftan kullanarak bir kullanarak devrettiği aşağıdaki örnekte gösterildiği gibi bildirimi:  
  
```  
#include <iostream>  
using namespace std;  
  
class Base  
{  
public:      
    Base() { cout << "Base()" << endl; }  
    Base(const Base& other) { cout << "Base(Base&)" << endl; }  
    explicit Base(int i) : num(i) { cout << "Base(int)" << endl; }  
    explicit Base(char c) : letter(c) { cout << "Base(char)" << endl; }  
  
private:  
    int num;  
    char letter;  
};  
  
class Derived : Base  
{  
public:  
    // Inherit all constructors from Base  
    using Base::Base;  
  
private:  
    // Can't initialize newMember from Base constructors.  
    int newMember{ 0 };  
};  
  
int main(int argc, char argv[])  
{  
    cout << "Derived d1(5) calls: ";   
    Derived d1(5);  
    cout << "Derived d1('c') calls: ";  
    Derived d2('c');  
    cout << "Derived d3 = d2 calls: " ;  
    Derived d3 = d2;  
    cout << "Derived d4 calls: ";  
    Derived d4;   
  
    // Keep console open in debug mode:  
    cout << endl << "Press Enter to exit.";  
    char in[1];  
    cin.getline(in, 1);  
    return 0;  
}  
  
/* Output:  
Derived d1(5) calls: Base(int)  
Derived d1('c') calls: Base(char)  
Derived d3 = d2 calls: Base(Base&)  
Derived d4 calls: Base()  
  
Press Enter to exit.  
  
```  
  
 Using deyimi, kapsam içine temel sınıfından türetilmiş sınıfta oluşturucuları için özdeş bir imzaya sahip olanlar dışında tüm oluşturucular getirir. Genel olarak, türetilen türetilen sınıfın yeni bir veri üyeleri bildirir, Oluşturucular veya oluşturucular kullanmak en iyisidir.  
  
 Bu tür bir taban sınıf belirtiyorsa sınıf şablonu türü bağımsız değişkenden tüm oluşturucular devrettiği:  
  
```  
template< typename T >  
class Derived : T {  
    using T::T;   // declare the constructors from T  
    // ...  
};  
  
```  
  
 Bu temel sınıflar özdeş bir imzaya sahip oluşturucuları varsa türetme sınıfı birden çok taban sınıflardan devralan olamaz.  
  
##  <a name="rules_for_declaring_constructors"></a>Oluşturucuları bildirme kuralları  
 Bir oluşturucu, sınıfıyla aynı ada sahiptir. Aşırı yüklenmiş işlevlere ilişkin kurallara uyularak herhangi bir sayıda oluşturucu bildirilebilir.  
  
 `argument-declaration-list` boş olabilir.  
  
 C++, aşağıdaki tabloda açıklanan iki özel oluşturucu türüne, yani varsayılan ve kopya oluşturucularına sahiptir.  
  
### <a name="default-and-copy-constructors"></a>Varsayılan ve Kopya Oluşturucuları  
  
|Oluşturucu Türü|Arguments|Amaç|  
|--------------------------|---------------|-------------|  
|Varsayılan oluşturucu|Bağımsız değişken olmadan çağrılabilir|Sınıf türünden varsayılan bir nesne oluşturur|  
|Kopya oluşturucu|Aynı sınıf türüne yapılan başvurunun tek bir bağımsız değişkenini kabul edebilir|Sınıf türünden nesneleri kopyalar|  
  
 Varsayılan oluşturucular bağımsız değişken olmadan çağrılabilir. Ancak, tüm bağımsız değişkenlerde varsayılanlar olduğu takdirde, bir bağımsız değişken listesiyle varsayılan bir oluşturucu bildirebilirsiniz. Benzer şekilde, kopya oluşturucuları aynı sınıf türüne yapılan başvurunun tek bir bağımsız değişkenini kabul etmelidir. Sonraki tüm bağımsız değişkenlerde varsayılanlar olduğu takdirde daha fazla bağımsız değişken sağlanabilir.  
  
 Hiçbir oluşturucu sağlamazsanız, derleyici varsayılan bir oluşturucu oluşturmaya çalışır. Kopya oluşturucu sağlamazsanız, derleyici bir tane oluşturmaya çalışır. Bu derleyici tarafından oluşturulan oluşturucular, genel üye işlevleri olarak kabul edilir. Bir nesne olan ve başvuru olmayan ilk bağımsız değişkenle bir kopya oluşturucu belirtirseniz bir hata oluşturulur.  
  
 Derleyici tarafından oluşturulan varsayılan bir oluşturucu, nesneyi ayarlar (daha önce açıklandığı gibi vftables ve vbtables'ı başlatır) ve temel sınıflar ve üyeler için varsayılan oluşturucuları çağırır, ancak başka işlem yapmaz. Temel sınıf ve üye oluşturucuları, yalnızca mevcut, erişilebilir ve açık durumdaysalar çağrılır.  
  
 Derleyici tarafından oluşturulan bir kopya oluşturucu, yeni bir nesne ayarlar ve kopyalanan nesnenin içeriği için üye düzeyinde bir kopyalama gerçekleştirilir. Temel sınıf veya üye oluşturucuları varsa çağrılır; yoksa, bit düzeyinde kopyalama gerçekleştirilir.  
  
 Bir sınıfın tüm temel ve üye sınıflarını `type` kabul kopya oluşturucuları sahip bir **const** bağımsız değişkeni, derleyicinin ürettiği kopyalama Oluşturucusu türden tek bir bağımsız değişken kabul **const** `type` **&**. Aksi takdirde, derleyicinin ürettiği kopyalama Oluşturucusu türden tek bir bağımsız değişken kabul `type`  **&** .  
  
 Bir oluşturucu başlatmak için kullanabileceğiniz bir **const** veya `volatile` olarak nesne ancak Oluşturucusu bildirilemez **const** veya `volatile`. Bir oluşturucu yalnızca yasal depolama sınıfı olan **satır içi**; diğer depolama sınıfı değiştiricisi, kullanmak da dahil olmak üzere `__declspec` anahtar sözcüğü bir oluşturucu derleyici hatası neden olur.  
  
 Statik üye işlevlerini çağırma stdcall kullanılır ve genel işlevler bildirilen ile **__stdcall** anahtar sözcüğü ve değişken bağımsız değişken listesi kullanmayın. Kullandığınızda **__stdcall** bir oluşturucu gibi bir statik olmayan üye işlevi on anahtar sözcüğü derleyici çağırma thiscall kullanır. "  
  
 Temel sınıfların oluşturucuları, türetilmiş sınıflar tarafından devralınmaz. Türetilmiş sınıf türünün bir nesnesi oluşturulurken, temel sınıf bileşenlerinden başlanır; ardından türetilmiş sınıf bileşenlerine geçilir. Tam nesne kısmı başlatılan her temel sınıfın Oluşturucusu derleyici kullanır (dışındaki sanal türetme durumda.  
  
##  <a name="explicitly_invoking_constructors"></a>Açıkça oluşturucular çağırma  
 Oluşturucular, belirli bir türden nesneler oluşturmak için bir programda açıkça çağrılabilir. Örneğin, bir çizginin uçlarını gösteren iki `Point` nesnesi oluşturmak için aşağıdaki kod yazılabilir:  
  
```  
DrawLine( Point( 13, 22 ), Point( 87, 91 ) );  
```  
  
 `Point` türünden iki nesne oluşturulur, `DrawLine` işlevine geçirilir ve ifadenin (işlev çağrısı) sonunda yok edilir.  
  
 Bir oluşturucunun açıkça çağrıldığı diğer bir bağlam da başlatmada görülür:  
  
```  
Point pt = Point( 7, 11 );  
```  
  
 `Point` türünden bir nesne oluşturulur ve `int` türünden iki bağımsız değişkeni kabul eden oluşturucu kullanılarak başlatılır.  
  
 Önceki iki örnekte olduğu gibi oluşturucular açıkça çağrılarak oluşturulan nesneler adsızdır ve oluşturuldukları ifadenin ömrüne sahiptir. Bu daha ayrıntılı olarak ele alınmıştır [geçici nesneler](../cpp/temporary-objects.md).  
  
 Nesne tamamen ayarlanmış olduğundan bir oluşturucu içindeki her üye işlevi çağırmak genellikle güvenlidir (Sanal tablolar başlatılmış ve benzeri) ilk satırın kullanıcı kodu yürütme önce. Ancak, yapı veya yok etme sırasında için Özet temel sınıf sanal üye işlevi çağırmak üye işlevi için güvensiz olabilir.  
  
 Oluşturucular sanal işlevleri çağırabilir. Sanal işlevler çağrıldığında çağrılan işlevi Oluşturucusu ait sınıf kendi (ya da kendi tabanları devralınan için) tanımlanan işlevdir. Aşağıdaki örnek, bir sanal işlev içinde bir oluşturucu çağrıldığında, ne olacağını gösterir:  
  
```  
// specl_calling_virtual_functions.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class Base  
{  
public:  
    Base();             // Default constructor.  
    virtual void f();   // Virtual member function.  
};  
  
Base::Base()  
{  
    cout << "Constructing Base sub-object\n";  
    f();                // Call virtual member function  
}                       //  from inside constructor.  
  
void Base::f()  
{  
    cout << "Called Base::f()\n";  
}  
  
class Derived : public Base  
{  
public:  
    Derived();          // Default constructor.  
    void f();           // Implementation of virtual  
};                      //  function f for this class.  
  
Derived::Derived()  
{  
    cout << "Constructing Derived object\n";  
}  
  
void Derived::f()  
{  
    cout << "Called Derived::f()\n";  
}  
  
int main()  
{  
    Derived d;  
}  
```  
  
 Önceki program çalıştırıldığında, bildirimi `Derived d` aşağıdaki olaylar dizisi neden olur:  
  
1.  Sınıf oluşturucusu `Derived` (`Derived::Derived`) olarak adlandırılır.  
  
2.  Gövdesini girme önce `Derived` sınıfının oluşturucusu, sınıf oluşturucusu `Base` (`Base::Base`) olarak adlandırılır.  
  
 `Base::Base`işlev çağrıları `f`, bir sanal işlev olduğu. Normalde, `Derived::f` çünkü adlı nesne `d` türü `Derived`. Çünkü `Base::Base` işlevi bir oluşturucu, nesne değil henüz, `Derived` türü ve `Base::f` olarak adlandırılır.  
  
