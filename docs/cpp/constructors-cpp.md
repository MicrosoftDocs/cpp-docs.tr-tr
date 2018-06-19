---
title: Oluşturucular (C++) | Microsoft Docs
ms.custom: ''
ms.date: 04/06/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- constructors [C++]
- objects [C++], creating
- instance constructors
ms.assetid: 3e9f7211-313a-4a92-9584-337452e061a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d34dff9c04491c25b2babfd4e7f0574bf7c6c609
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32418132"
---
# <a name="constructors-c"></a>Oluşturucular (C++)

Sınıf üyeleri nasıl başlatılır özelleştirme ya da, sınıfın bir nesnesi oluşturulduğunda işlevleri çağırmak için tanımlamak bir *Oluşturucusu*. Bir oluşturucu sınıf ve hiçbir değer döndürmeyen aynı ada sahip. Başlatma çeşitli şekillerde özelleştirmek için gereken sayıda aşırı yüklü oluşturucular tanımlayabilirsiniz. Genellikle, sınıf tanımı veya devralma hiyerarşisi dışındaki kodu sınıfın nesnelerini oluşturabilmesi için ortak erişilebilirlik oluşturucular vardır. Ancak bir oluşturucu olarak da bildirebilirsiniz **korumalı** veya **özel**.

Oluşturucular, isteğe bağlı olarak bir üye init listesi alabilir. Bu sınıf üyeleri Oluşturucusu gövdesindeki değerler atama daha başlatmak için daha etkili bir yoludur. Aşağıdaki örnek, bir sınıfı gösterir `Box` üç oluşturucular aşırı yüklendi. Son iki üye init listelerini kullanın:

```cpp

class Box {
public:
    // Default constructor
    Box() {}

    // Initalize a Box with equal dimensions (i.e. a cube)
    explicit Box(int i) : m_width(i), m_length(i), m_height(i) // member init list
    {}

    // Initialize a Box with custom dimensions
    Box(int width, int length, int height)
        : m_width(width), m_length(length), m_height(height)
    {}

    int Volume() { return m_width * m_length * m_height; }

private:
    // Will have value of 0 when default constructor is called.
    // If we didn't zero-init here, default constructor would
    // leave them uninitialized with garbage values.
    int m_width{ 0 };
    int m_length{ 0 };
    int m_height{ 0 };
};

```

Sınıfının bir örneği bildirirken derleyici çağırmak için hangi Oluşturucusu aşırı çözüm kurallara göre seçti:

```cpp

int main()
{
    Box b; // Calls Box()

    // Using uniform initialization (preferred):
    Box b2 {5}; // Calls Box(int)
    Box b3 {5, 8, 12}; // Calls Box(int, int, int)

    // Using function-style notation:
    Box b4(2, 4, 6); // Calls Box(int, int, int)
}

```

- Oluşturucular olarak bildirilebilir **satır içi**, [açık](#explicit_constructors), **arkadaş** veya [constexpr](#constexpr_constructors).
- Bir oluşturucu olarak bildirilen bir nesne başlatabilir **const**, **volatile** veya **const geçici**. Nesne haline gelir **const** Oluşturucusu tamamlandıktan sonra.
- Bir uygulama dosyasında bir oluşturucu tanımlamak için bir tam ad işleviyle herhangi diğer üye olarak verin: `Box::Box(){...}`.

## <a name="member_init_list"></a> Üye Başlatıcı Listeleri

Bir oluşturucu isteğe bağlı olarak sınıf üyeleri Oluşturucusu gövde yürütülmesi önce başlatır üye başlatıcı listesi olabilir. (Bir üye başlatıcı listesi aynı olmadığını unutmayın bir *başlatıcı listesi* türü [std::initializer_list\<T >](../standard-library/initializer-list-class.md).)

Üye ıntializer listesini kullanarak doğrudan üye başlatır çünkü Oluşturucusu gövdesinde değerler atama üzerinden tercih edilir. Aşağıdaki örnekte liste oluşur tüm üye başlatıcıdan gösterir **identifier(argument)** ifadeleri iki nokta üst üste sonra:

```cpp
  
    Box(int width, int length, int height)
        : m_width(width), m_length(length), m_height(height)
    {}
```

Tanımlayıcı için bir sınıf üyesi başvurması gerekir; bağımsız değişken değerle başlatılır. Bağımsız değişken Oluşturucu parametrelerden biri, bir işlev çağrısı olabilir veya bir [std::initializer_list\<T >](../standard-library/initializer-list-class.md). 

**const** üyeleri ve başvuru türündeki üye, üye Başlatıcı listesinde başlatılmalıdır.

Parametreli temel sınıf oluşturucular çağrıları Başlatıcı listesinde temel sınıf türetilmiş Oluşturucusu yürütme önce tam olarak başlatılmadan sağlamak için yapılması gerekir.

## <a name="default_constructors"></a> Varsayılan Oluşturucu

 *Varsayılan oluşturucular* genellikle parametresi olmayan, ancak parametreleri varsayılan değerlere sahip olabilir.

```cpp
class Box {
public:
    Box() { /*perform any required default initialization steps*/}

    // All params have default values
    Box (int w = 1, int l = 1, int h = 1): m_width(w), m_height(h), m_length(l){}
...
}
```

Varsayılan Oluşturucu biri olan [özel üye işlevleri](special-member-functions.md). Bir sınıf oluşturucu yok bildirilir, derleyici örtülü sağlar **satır içi** varsayılan oluşturucu.

```cpp
#include <iostream>
using namespace std;

class Box {
public:
    int Volume() {return m_width * m_height * m_length;}
private:
    int m_width { 0 };
    int m_height { 0 };
    int m_length { 0 };
};

int main() {
    Box box1; // Invoke compiler-generated constructor
    cout << "box1.Volume: " << box1.Volume() << endl; // Outputs 0
}

```

Örtük varsayılan kurucu üzerinde güveniyorsanız, önceki örnekte gösterildiği gibi sınıf tanımının üyelerinde başlatmak emin olun. Bu başlatıcıları olmadan üyeleri başlatılmamış olacaktır ve Volume() çağrısı çöp değer oluşturur. Genel olarak, bir örtük varsayılan oluşturucu bile bağlı değil, bu şekilde üyeleri başlatmak iyi bir uygulamadır.

Olarak tanımlayarak örtük varsayılan bir Oluşturucu Oluşturma derleyici engelleyebilirsiniz [silinmiş](#explicitly_defaulted_and_deleted_constructors):

```cpp

    // Default constructor
    Box() = delete;

```

Derleyicinin ürettiği varsayılan bir oluşturucu herhangi bir sınıf üye varsayılan oluşturulabilir değilse silindi olarak tanımlanır. Varsayılan bir oluşturucu ve erişilebilir Yıkıcılar Örneğin, sınıf türdeki tüm üyelerin ve sınıf türü üyeleri olmalıdır. Tüm veri üyeleri başvuru türü, de olarak **const** üyeleri varsayılan üye başlatıcıdan olması gerekir.

Derleyicinin ürettiği varsayılan bir oluşturucu çağırın ve parantez kullanmaya çalıştığınızda, bir uyarı verilir:

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
    Box box3; // C2512: no appropriate default constructor available
}

```

Bir sınıfın varsayılan oluşturucusu yoksa, o sınıfa ait nesneler dizisi yalnızca köşeli paranteze sahip bir sözdizimi kullanılarak oluşturulamaz. Örneğin önceki kod bloğu düşünüldüğünde, bir Kutular dizisi şu şekilde bildirilemez:

```cpp
Box boxes[3]; // C2512: no appropriate default constructor available

```

Ancak, kutusunu nesnelerinin bir dizisi başlatmak için bir dizi Başlatıcı listeleri kullanabilirsiniz:

```cpp
Box boxes[3]{ { 1, 2, 3 }, { 4, 5, 6 }, { 7, 8, 9 } };
```

Daha fazla bilgi için bkz: [başlatıcıları](initializers.md).

## <a name="copy_and_move_constructors"></a> Kopya oluşturucuları

A *kopya Oluşturucu* aynı türde bir nesneden üye değerlerinin kopyalayarak bir nesneyi başlatır. Sınıf üyeleri skaler değerler gibi tüm basit türler, derleyicinin ürettiği kopyalama Oluşturucusu yeterlidir ve, tanımlamak kendi gerekmez. Sınıfınıza daha karmaşık başlatma gerektiriyorsa, özel kopya Oluşturucu uygulamak için gerekir. Bir işaretçi bir sınıf üyesi ise, örneğin, daha sonra yeni bellek ayırabilir ve diğer kişinin işaret için nesneden değerleri kopyalamak için kopya Oluşturucu tanımlamanız gerekir. Derleyicinin ürettiği kopyalama Oluşturucusu yalnızca işaretçi kopyalar, böylece yeni işaretçi hala diğerinin bellek konumuna işaret.

Kopya Oluşturucu bu imzaları birine sahip:

```cpp

    Box(Box& other); // Avoid if possible--allows modification of other.
    Box(const Box& other);
    Box(volatile Box& other);
    Box(volatile const Box& other);

    // Additional parameters OK if they have default values
    Box(Box& other, int i = 42, string label = "Box");
```

Kopya Oluşturucu tanımladığınızda, bir kopya atama işleci (=) tanımlamanız gerekir. Daha fazla bilgi için bkz: [atama](assignment.md) ve [kopyalama oluşturucular ve atama işleçleri kopyalama](copy-constructors-and-copy-assignment-operators-cpp.md).

Kopya Oluşturucu silindi olarak tanımlayarak kopyalanmasını nesnenizin engel olabilirsiniz:

```cpp
    Box (const Box& other) = delete;
```

Nesne kopyalanmaya çalışılırken hata üretir *C2280: silinen işlevi başvuru girişimi*.

## <a name="move_constructors"></a> Taşıma oluşturucuları
A *taşıma Oluşturucusu* özgün veri kopyalama olmadan yeni bir değişken mevcut nesnenin verileri sahipliğini taşır özel üye işlevdir. Birinci parametre olarak rvalue başvuru alır ve ek parametreleri varsayılan değerlere sahip olmalıdır. Büyük nesneleri etrafında geçirilirken taşıma oluşturucuları programınızın verimliliğini önemli ölçüde artırabilir. Bir taşıma oluşturucusuna rvalue başvuru kendi ilk parametre olarak alır. Diğer parametreleri varsayılan değerlere sahip olmalıdır.

```cpp
Box(Box&& other);
```

Derleyici bir taşıma oluşturucusuna kaynakları nesne yok edilmesi ve artık ihtiyaç aynı türde başka bir nesne tarafından nerede başlatıldığını bazı durumlarda seçer. Bir taşıma oluşturucusuna aşırı yükleme çözümü tarafından seçildiğinde aşağıdaki örnekte bir örnek gösterilmektedir. Değişkeni *kutusunu* get_Box() tarafından döndürülen olan bir *xvalue* (süresi dolan değer) olduğu hakkında kapsamının dışına gitmek için. Bu örnek gerekçesi sağlamak için şirketinizdeki kutusunun içeriğini temsil eden dizeleri büyük bir vektör verin. "Vektör şimdi yeni nesneye ait böylece vektör ve onun dizeleri kopyalamak yerine taşıma oluşturucusu, süresi dolan değerinden"kutu"çalar". Çağrı `std::move` için gerekli olan tek şey her ikisi de `vector` ve `string` sınıfları kendi taşıma oluşturucuları uygulayın.

```cpp
#include <iostream>
#include <vector>
#include <string>
#include <algorithm>
using namespace std;


class Box {
public:
    Box() { std::cout << "default" << std::endl; }
    Box(int width, int height, int length)
       : m_width(width), m_height(height), m_length(length)
    {
        std::cout << "int,int,int" << std::endl;
    }
    Box(Box& other)
       : m_width(other.m_width), m_height(other.m_height), m_length(other.m_length)
    {
        std::cout << "copy" << std::endl;
    }
    Box(Box&& other) : m_width(other.m_width), m_height(other.m_height), m_length(other.m_length)
    {
        m_contents = std::move(other.m_contents);
        std::cout << "move" << std::endl;
    }
    int Volume() { return m_width * m_height * m_length; }
    void Add_Item(string item) { m_contents.push_back(item); }
    void Get_Contents()
    {
        for (const auto& item : m_contents)
        {
            cout << item << " ";
        }
    }
private:
    int m_width{ 0 };
    int m_height{ 0 };
    int m_length{ 0 };
    vector<string> m_contents;
};

Box get_Box()
{
    Box b(5, 10, 18); // "int,int,int"
    b.Add_Item("Toupee");
    b.Add_Item("Megaphone");
    b.Add_Item("Suit");

    return b;
}

int main()
{
    Box b; // "default"
    Box b1(b); // "copy"
    Box b2(get_Box()); // "move"
    cout << "b2 contents: ";
    b2.Get_Contents(); // Prove that we have all the values

    char ch;
    cin >> ch; // keep window open
    return 0;
}


```

Bir sınıf bir taşıma oluşturucusuna tanımlamıyorsa derleyici hiçbir kullanıcı bildirilen kopya Oluşturucu, kopya atama işleci, taşıma atama işleci veya yıkıcı ise örtük bir oluşturur. Hiçbir açık veya örtülü taşıma oluşturucusuna tanımlanırsa, aksi takdirde bir taşıma oluşturucusuna kullanırsınız işlemleri kopya Oluşturucu kullanın. Bir sınıf bir taşıma oluşturucusuna veya taşıma atama işleci bildirirse, örtük olarak bildirilen kopya Oluşturucu silindi olarak tanımlanır.

Örtük olarak bildirilen taşıma oluşturucusuna sınıf türleri olan herhangi bir üye bir yıkıcı olmaması veya derleyici taşıma işlemi için kullanılmak üzere hangi Oluşturucusu belirleyemiyor silindi olarak tanımlanır.

Önemsiz olmayan taşıma oluşturucusuna yazma hakkında daha fazla bilgi için bkz: [taşıma oluşturucuları ve taşıma atama işleçleri (C++)](../cpp/move-constructors-and-move-assignment-operators-cpp.md).

## <a name="explicitly_defaulted_and_deleted_constructors"></a> Açıkça varsayılan haline getirilen ve Silinen oluşturucular

Açıkça yapabilecekleriniz *varsayılan* kopyalama Oluşturucular, varsayılan Oluşturucular, Oluşturucular taşımak, atama işleçleri kopyalayın, Yıkıcılar getirip atama işleçleri. Açıkça yapabilecekleriniz *silmek* tüm özel üye işlevleri.

```cpp
class Box
{
public:
    Box2() = delete;
    Box2(const Box2& other) = default;
    Box2& operator=(const Box2& other) = default;
    Box2(Box2&& other) = default;
    Box2& operator=(Box2&& other) = default;
    //...
};
```

Daha fazla bilgi için bkz: [açıkça varsayılan ve Silinen işlevler](../cpp/explicitly-defaulted-and-deleted-functions.md).

## <a name="constexpr_constructors"></a> constexpr oluşturucular

Bir oluşturucu olarak bildirilmelidir [constexpr](constexpr-cpp.md) varsa

- tüm koşulları karşılayan yoksa ya da varsayılan olarak bildirilen olan [constexpr işlevleri](constexpr-cpp.md#constexpr_functions) genel olarak;
- sınıf hiçbir sanal taban sınıflar; yine de sahip istiyor musunuz?
- parametrelerden biri her bir [değişmez değer türü](trivial-standard-layout-and-pod-types.md#literal_types);
- gövdesi bir işlev try bloğu değil;
- tüm statik olmayan veri üyeleri ve temel sınıf alt nesneler başlatılır;
- sınıf (a) değişken üyeleri sahip UNION ise, veya (b) anonim birleşimler varsa, yalnızca bir birleşim üyeleri başlatılır;
- her sınıf türü statik olmayan veri üyesi ve tüm temel sınıf alt nesneler constexpr oluşturucuya sahip


## <a name="init_list_constructors"></a> Başlatıcı listesi oluşturucular

Bir oluşturucu uzun sürerse bir [std::initializer_list\<T\> ](../standard-library/initializer-list-class.md) , parametre ve herhangi bir parametre varsayılan bağımsız değişkenler gibi sınıfı olduğunda bu Oluşturucusu aşırı yük çözüm seçilir doğrudan başlatma örneği. İnitializer_list kabul edebilir herhangi bir üyesi başlatmak için kullanabilirsiniz. Örneğin, (daha önce gösterilen) Box sınıfı olduğunu varsayalım bir `std::vector<string>` üye **m_contents**. Böyle bir oluşturucu sağlayabilirsiniz:

```cpp
    Box(initializer_list<string> list, int w = 0, int h = 0, int l = 0)
        : m_contents(list), m_width(w), m_height(h), m_length(l)
{}
```

Ve kutusunu nesneleri bu gibi oluşturun:

```cpp
    Box b{ "apples", "oranges", "pears" }; // or ...
    Box b2(initializer_list<string> { "bread", "cheese", "wine" }, 2, 4, 6);
```

## <a name="explicit_constructors"></a> Açıkça oluşturucular

Bir sınıfın tek bir parametre ile bir oluşturucu varsa veya biri dışındaki tüm parametreler varsayılan bir değer varsa, parametre türü örtük olarak sınıfı türüne dönüştürülebilir. Örneğin, varsa `Box` sınıfı şöyle bir oluşturucu sahiptir:

```cpp
Box(int size): m_width(size), m_length(size), m_height(size){}
```

Böyle bir kutusunu başlatma mümkündür:

```cpp
Box b = 42;
```

Veya bir kutusu götüren bir işleve int geçirebilirsiniz:

```cpp
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

Bu tür dönüşümleri bazı durumlarda yararlı olabilir, ancak daha sık Zarif ancak ciddi hatalar, kodunuzda açabilir. Genel kural olarak, kullanması gereken **açık** anahtar sözcüğü bu tür bir örtük tür dönüştürmesi önlemek için bir oluşturucu (ve kullanıcı tanımlı işleçler):

```cpp

explicit Box(int size): m_width(size), m_length(size), m_height(size){}
```

Oluşturucusu açık olduğunda, bu satırın derleyici hatası neden olur: `ShippingOrder so(42, 10.8);`.  Daha fazla bilgi için bkz: [kullanıcı tanımlı tür dönüşümleri](../cpp/user-defined-type-conversions-cpp.md).

## <a name="order_of_construction"></a> Yapı sırası

Bir oluşturucu kendi işini şu sırayla gerçekleştirir:

1. Temel sınıfı ve üye oluşturucuları bildirim sırasına göre çağırır.

2. Sınıf sanal temel sınıflardan türetilmişse, nesnenin sanal taban işaretçilerini başlatır.

3. Sınıf sanal işlevler içeriyorsa ya da devralıyorsa, nesnenin sanal işlev işaretçilerini başlatır. Sanal işlev işaretçileri, sanal işlev çağrılarının koda doğru bağlanmasını sağlamak için sınıfın sanal işlev tablosunu gösterir.

4. Kendi işlev gövdesindeki tüm kodları yürütür.

Aşağıdaki örnek, türetilmiş bir sınıfın oluşturucusundaki temel sınıfın ve üye oluşturucuların çağrılma sırasını göstermektedir. Önce taban oluşturucu çağrılır, sonra taban sınıfı üyeleri sınıf bildiriminde görüldükleri sırayla başlatılır ve ardından türetilen oluşturucu çağrılır.

```cpp

#include <iostream>

using namespace std;

class Contained1 {
public:
    Contained1() { cout << "Contained1 ctor\n"; }
};

class Contained2 {
public:
    Contained2() { cout << "Contained2 ctor\n"; }
};

class Contained3 {
public:
    Contained3() { cout << "Contained3 ctor\n"; }
};

class BaseContainer {
public:
    BaseContainer() { cout << "BaseContainer ctor\n"; }
private:
    Contained1 c1;
    Contained2 c2;
};

class DerivedContainer : public BaseContainer {
public:
    DerivedContainer() : BaseContainer() { cout << "DerivedContainer ctor\n"; }
private:
    Contained3 c3;
};

int main() {
    DerivedContainer dc;
}

```

Çıkış şu şekildedir:

```output
Contained1 ctor
Contained2 ctor
BaseContainer ctor
Contained3 ctor
DerivedContainer ctor
```

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

Bir oluşturucu özel bir durum oluşturursa, yok etme sırası oluşturma sırasının tersidir:

1. Oluşturucu işlevinin gövdesindeki kod geriye doğru çözülür.

1. Temel sınıf ve üye nesneleri bildirimin tersi sırada yok edilir.

1. Oluşturucu temsil eden değilse, tam oluşturulmuş tüm taban sınıfı nesneleri ve üyeleri yok edilir. Ancak nesnenin kendisi tam oluşturulmadığından yok edici çalışmaz.

### <a name="constructors-for-classes-that-have-multiple-inheritance"></a>Birden çok devralma olan sınıf oluşturucuları

Bir sınıf birden çok temel sınıftan türetiliyorsa, temel sınıf oluşturucuları türetilen sınıfın bildirimi içinde listelendikleri sırayla çağrılır:

```cpp
#include <iostream>
using namespace std;

class BaseClass1 {
public:
    BaseClass1() { cout << "BaseClass1 ctor\n"; }
};
class BaseClass2 {
public:
    BaseClass2() { cout << "BaseClass2 ctor\n"; }
};
class BaseClass3 {
public:
    BaseClass3() { cout << "BaseClass3 ctor\n"; }
};
class DerivedClass : public BaseClass1,
                     public BaseClass2,
                     public BaseClass3
                     {
public:
    DerivedClass() { cout << "DerivedClass ctor\n"; }
};

int main() {
    DerivedClass dc;
}

```

Aşağıdaki çıktıyı beklemelisiniz:

```output

BaseClass1 ctor
BaseClass2 ctor
BaseClass3 ctor
DerivedClass ctor

```

## <a name="virtual_functions_in_constructors"></a> Oluşturucular içinde sanal işlevleri

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

```output
BaseClass print_it
Derived Class print_it
```

## <a name="delegating_constructors"></a> Oluşturucular için temsilci seçme

A *oluşturucusu için temsilci seçme* farklı bir oluşturucu başlatma işinin bir kısmını yapmak için aynı sınıfta çağırır. Bu, tüm benzer iş gerçekleştirmek zorunda birden çok oluşturucular olduğunda yararlıdır. Bir oluşturucuda asıl mantığı yazmak ve başkalarından çağırma. Aşağıdaki basit örnekte, Box(int) Box(int,int,int) kendi iş atar:

```cpp
class Box {
public:
    // Default constructor
    Box() {}

    // Initalize a Box with equal dimensions (i.e. a cube)
    Box(int i) :  Box(i, i, i);  // delegating constructor
    {}

    // Initialize a Box with custom dimensions
    Box(int width, int length, int height)
        : m_width(width), m_length(length), m_height(height)
    {}
    //... rest of class as before
};
```


Herhangi bir oluşturucunun işi biter bitmez, oluşturucular tarafından oluşturulan nesne tamamen başlatılır. Daha fazla bilgi için bkz: [tek düzen başlatma ve oluşturucuları temsilci](../cpp/uniform-initialization-and-delegating-constructors.md).

## <a name="inheriting_constructors"></a> Oluşturucular (C ++ 11) devralma

Türetilmiş bir sınıf oluşturucular doğrudan bir taban sınıftan kullanarak bir kullanarak devrettiği aşağıdaki örnekte gösterildiği gibi bildirimi:

```cpp
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

int main()
{
    cout << "Derived d1(5) calls: ";
    Derived d1(5);
    cout << "Derived d1('c') calls: ";
    Derived d2('c');
    cout << "Derived d3 = d2 calls: " ;
    Derived d3 = d2;
    cout << "Derived d4 calls: ";
    Derived d4;
}

/* Output:
Derived d1(5) calls: Base(int)
Derived d1('c') calls: Base(char)
Derived d3 = d2 calls: Base(Base&)
Derived d4 calls: Base()*/

```

Using deyimi, kapsam içine temel sınıfından türetilmiş sınıfta oluşturucuları için özdeş bir imzaya sahip olanlar dışında tüm oluşturucular getirir. Genel olarak, türetilen türetilen sınıfın yeni bir veri üyeleri bildirir, Oluşturucular veya oluşturucular kullanmak en iyisidir.

Bu tür bir taban sınıf belirtiyorsa sınıf şablonu türü bağımsız değişkenden tüm oluşturucular devrettiği:

```cpp
template< typename T >
class Derived : T {
    using T::T;   // declare the constructors from T
    // ...
};

```

Bu temel sınıflar özdeş bir imzaya sahip oluşturucuları varsa türetme sınıfı birden çok taban sınıflardan devralan olamaz.

## <a name="constructors_in_composite_classes"></a> Oluşturucular ve bileşik sınıfları

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