---
title: Oluşturucular (C++)
ms.date: 04/06/2018
helpviewer_keywords:
- constructors [C++]
- objects [C++], creating
- instance constructors
ms.assetid: 3e9f7211-313a-4a92-9584-337452e061a9
ms.openlocfilehash: 91d85f62917ff722a61ecbc87c58379a00016b83
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51523162"
---
# <a name="constructors-c"></a>Oluşturucular (C++)

Sınıf üyeleri nasıl başlatılır özelleştirme veya sınıfının bir nesnesi oluşturulduğunda işlevleri çağırmak için tanımlamak bir *Oluşturucusu*. Bir oluşturucu sınıf ve dönüş değeri ile aynı ada sahiptir. Çok çeşitli yollarla başlatma özelleştirmek için gerektiği şekilde aşırı yüklü oluşturucular tanımlayabilirsiniz. Genellikle, sınıf tanımı veya devralma hiyerarşisi dışındaki kod sınıfın nesneleri oluşturabilmesi ortak erişilebilirlik oluşturucular sahiptir. Ancak bir oluşturucu olarak da bildirebilirsiniz **korumalı** veya **özel**.

Oluşturucular, isteğe bağlı olarak bir üye init listesini alabilir. Bu sınıf üyeleri Oluşturucusu gövdesinde değerler atayarak daha başlatmak için daha etkili bir yoludur. Aşağıdaki örnek, bir sınıfı gösterir `Box` üç aşırı yüklü oluşturucular. Son iki üye başlatma listeleri kullanın:

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

Bir sınıf örneği bildirdiğinizde, derleyici çağırmak için hangi kurucu aşırı yükleme çözünürlüğü kurallara göre seçer:

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

- Oluşturucular olarak belirtilebilir **satır içi**, [açık](#explicit_constructors), **arkadaş** veya [constexpr](#constexpr_constructors).
- Bir oluşturucu olarak bildirilen bir nesne başlatabilirsiniz **const**, **geçici** veya **const volatile**. Nesne haline gelir **const** Oluşturucu tamamlandıktan sonra.
- Bir uygulama dosyasında bir kurucu tanımlamak için bu tam adı ile diğer üye bir işlev olarak verin: `Box::Box(){...}`.

## <a name="member_init_list"></a> Üye Başlatıcı Listeleri

Bir oluşturucu, isteğe bağlı olarak sınıfı üyeleri Oluşturucusu gövdenin yürütülmesi önce başlatan bir üye başlatıcı listesi olabilir. (Bir üye başlatıcı listesi olarak aynı şey olmadığını unutmayın bir *başlatıcı listesi* türü [std::initializer_list\<T >](../standard-library/initializer-list-class.md).)

Bir üye Başlatıcısı listesini kullanarak doğrudan üye başlatır çünkü Oluşturucu gövdesinde değerler atama üzerinden tercih edilir. Aşağıdaki örnekte üye başlatıcı listesi oluşan tüm gösterir **identifier(argument)** sonra iki nokta üst üste ifadeleri:

```cpp
    Box(int width, int length, int height)
        : m_width(width), m_length(length), m_height(height)
    {}
```

Tanımlayıcı, bir sınıf üyesine başvurmalıdır; bağımsız değişkenin değeri ile başlatıldı. Bağımsız değişken Oluşturucu parametrelerden biri, bir işlev çağrısı olabilir veya [std::initializer_list\<T >](../standard-library/initializer-list-class.md).

**const** üyeleri ve üyeleri başvuru türündeki üye Başlatıcı listesinde başlatılmalıdır.

Parametreli bir temel sınıf oluşturucuları çağrısına, temel sınıfı türetilen Oluşturucu yürütülmesini önce tam olarak başlatılmadan emin olmak için Başlatıcı listesinde yapılmalıdır.

## <a name="default_constructors"></a> Varsayılan Oluşturucu

*Varsayılan oluşturucular* genellikle parametresiz olmalıdır, ancak varsayılan değeri olan parametrelere sahip olabilir.

```cpp
class Box {
public:
    Box() { /*perform any required default initialization steps*/}

    // All params have default values
    Box (int w = 1, int l = 1, int h = 1): m_width(w), m_height(h), m_length(l){}
...
}
```

Varsayılan oluşturucular biri olan [özel üye işlevleri](special-member-functions.md). Bir sınıf içinde hiç bir oluşturucu bildirilirse, derleyici örtük sağlar **satır içi** varsayılan oluşturucu.

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

Örtülü varsayılan bir oluşturucu kullanırsanız, önceki örnekte gösterildiği gibi sınıf tanımının üye başlatma emin olun. Bu başlatıcılar olmadan üye başlatılmamış ve Volume() aramayı çöp değeri oluşturur. Genel olarak, bu şekilde üyeleri üzerinde örtülü varsayılan bir oluşturucuya bağlı değil bile, Başlat iyi bir uygulamadır.

Derleyici olarak tanımlayarak bir örtülü varsayılan oluşturucu oluşturmasını engelleyebilirsiniz [silinmiş](#explicitly_defaulted_and_deleted_constructors):

```cpp
    // Default constructor
    Box() = delete;
```

Derleyicinin ürettiği varsayılan oluşturucu tüm sınıf üyeleri varsayılan atmamalıdır değilse silindi olarak tanımlanır. Varsayılan bir oluşturucu ve erişilebilir bir yok ediciler, sınıf türünün tüm üyeleri ve sınıf türü üyeleri olmalıdır. Tüm veri üyelerini başvuru türü, de olarak **const** üyeleri varsayılan üye başlatıcıya sahip olmalıdır.

Derleyicinin ürettiği varsayılan bir oluşturucuyu çağırdığınızda ve parantez kullanmaya çalıştığınızda, bir uyarı verilir:

```cpp
class myclass{};
int main(){
myclass mc();     // warning C4930: prototyped function not called (was a variable definition intended?)
}
```

Bu, En Çok Güçlük Çıkaran Ayrıştırma sorununa bir örnektir. Örnek ifade bir işlevin bildirimi ya da varsayılan bir oluşturucunun çağrılması olarak yorumlanabileceğinden ve C++ ayrıştırıcıları diğer şeylere oranla bildirimlere öncelik verdiğinden, ifade bir işlev bildirimi olarak ele alınır. Daha fazla bilgi için [en çok güçlük çıkartan ayrıştırma](http://en.wikipedia.org/wiki/Most_vexing_parse).

Varsayılan olmayan bir oluşturucu bildirilirse, derleyici varsayılan bir oluşturucu sağlamaz:

```cpp
class Box {
public:
    Box(int width, int length, int height)
        : m_width(width), m_length(length), m_height(height){}
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

Ancak, bir dizi Başlatıcı Listeleri kutusu nesnelerinin bir dizisi başlatmak için kullanabilirsiniz:

```cpp
Box boxes[3]{ { 1, 2, 3 }, { 4, 5, 6 }, { 7, 8, 9 } };
```

Daha fazla bilgi için [başlatıcılar](initializers.md).

## <a name="copy_and_move_constructors"></a> Kopya oluşturucuları

A *kopya Oluşturucu* nesneyi aynı türde bir nesneden üye değerlerinin kopyalayarak başlatır. Sınıf üyesi skaler değerler gibi tüm basit türler, derleyici tarafından oluşturulan kopya Oluşturucu yeterlidir ve, tanımlamak kendi ihtiyacınız yoktur. Sınıfınıza daha karmaşık başlatma gerektiriyorsa, özel kopya Oluşturucu yapması gerekir. Bir sınıf üyesine bir işaretçi ise, örneğin, daha sonra yeni bellek ayırmak ve değerleri diğer tarafın işaret edilen nesneyi kopyalamak için bir kopya Oluşturucu tanımlamanız gerekir. Derleyici tarafından oluşturulan kopya Oluşturucu, yalnızca yeni işaretçi yine de diğer tarafın bellek konumuna işaret eden işaretçi kopyalar.

Kopya Oluşturucu bu imzalar birine sahip:

```cpp
    Box(Box& other); // Avoid if possible--allows modification of other.
    Box(const Box& other);
    Box(volatile Box& other);
    Box(volatile const Box& other);

    // Additional parameters OK if they have default values
    Box(Box& other, int i = 42, string label = "Box");
```

Kopya Oluşturucu tanımladığınızda, kopya atama işleci (=) da tanımlamanız gerekir. Daha fazla bilgi için [atama](assignment.md) ve [oluşturucuları kopyalama ve atama işleçlerini kopyalayın](copy-constructors-and-copy-assignment-operators-cpp.md).

Kopya Oluşturucu silindi olarak tanımlayarak kopyalanmasını nesnenizin engelleyebilirsiniz:

```cpp
    Box (const Box& other) = delete;
```

Nesne kopyalamaya çalışırken hata üreten *C2280: silinmiş bir işleve başvurmaya çalışıyor*.

## <a name="move_constructors"></a> Taşıma oluşturucuları

A *taşıma Oluşturucu* özgün veri kopyalama olmadan yeni bir değişken için var olan nesnenin veri sahipliğini taşıyan özel üye işlevi olmasıdır. İlk parametre olarak bir rvalue başvurusunu alır ve herhangi ek bir parametre varsayılan değerlere sahip olmalıdır. Büyük nesnelerin çevresinde geçirirken, taşıma oluşturucuları, programınızın verimliliğini önemli ölçüde artırabilir. Taşıma Oluşturucusu bir rvalue başvurusunu kendi ilk parametre olarak alır. Herhangi bir parametre varsayılan değerlere sahip olmalıdır.

```cpp
Box(Box&& other);
```

Derleyici bir taşıma Oluşturucusu kaynakları burada nesne edilmek üzere olduğunu ve artık ihtiyaç duyduğu aynı türde başka bir nesne tarafından Başlatılmakta olan bazı durumlarda seçer. Aşağıdaki örnek, bir taşıma kurucu aşırı yükleme çözünürlüğü tarafından seçildiğinde bir servis talebi gösterir. Değişken *kutusu* get_Box() tarafından döndürülen olduğu bir *xvalue* (süresi dolan değer) olduğu kapsam dışına geçmek için. Bu örneğin motivasyon sağlamak için şimdi kutusunun içeriğini temsil eden dizeleri büyük bir vektör verin. "Böylece vektör artık yeni nesneye ait vektör ve kendi dizeleri kopyalamak yerine, taşıma Oluşturucu, süresi dolan değerini"kutu"sızmasının". Çağrı `std::move` için gerekli olan tüm hem `vector` ve `string` sınıfları kendi taşıma oluşturucuları uygulayın.

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

Bir sınıf bir taşıma Oluşturucu tanımlamıyorsa, hiçbir kullanıcı bildirilen kopya Oluşturucu, kopya atama işleci, taşıma atama işleci veya yıkıcı ise, derleyici örtük bir oluşturur. Hiçbir açık veya örtülü taşıma Oluşturucusu tanımlanmazsa, aksi takdirde bir taşıma Oluşturucusu kullanacağınız operations kopya Oluşturucu kullanın. Bir sınıf, bir taşıma Oluşturucusu veya taşıma atama işleci bildirirse, örtük olarak bildirilmiş bir kopya Oluşturucu silindi olarak tanımlanmış.

Örtük olarak bildirilmiş bir taşıma Oluşturucusu bir yok Edicisi olan sınıf türleri herhangi bir üye eksik ya da derleyici taşıma işlemi için kullanılacak hangi oluşturucunun belirlenemiyor silindi olarak tanımlanmış.

Önemsiz taşıma Oluşturucusu yazma hakkında daha fazla bilgi için bkz. [taşıma oluşturucuları ve taşıma atama işleçleri (C++)](../cpp/move-constructors-and-move-assignment-operators-cpp.md).

## <a name="explicitly_defaulted_and_deleted_constructors"></a> Açıkça varsayılan yapılmış ve silinmiş oluşturucular

Açıkça yapabilecekleriniz *varsayılan* oluşturucuları kopyalama, varsayılan oluşturucu, taşıma oluşturucuları, atama işleçlerini kopyalayın, Yıkıcılar taşıma atama işleçleri. Açıkça yapabilecekleriniz *Sil* tüm özel üye işlevleri.

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

Daha fazla bilgi için [açıkça varsayılan ve silinmiş işlevler](../cpp/explicitly-defaulted-and-deleted-functions.md).

## <a name="constexpr_constructors"></a> constexpr oluşturucular

Bir oluşturucu olarak bildirilebilir [constexpr](constexpr-cpp.md) varsa

- için tüm koşulları karşılayan yoksa ya da varsayılan olarak bildirilmiş olan [constexpr işlevleri](constexpr-cpp.md#constexpr_functions) genel olarak;
- sınıf sanal temel sınıfa sahip;
- Her parametre bir [değişmez değer türü](trivial-standard-layout-and-pod-types.md#literal_types);
- gövdesi bir işlev try bloğu değil;
- tüm statik olmayan veri üyeleri ve temel sınıf alt nesneler başlatılır;
- sınıf (a) bir birleşimdir değişken üyelerinin olması ya da (b) olan anonim birleşimler, yalnızca bir birleşim üyeleri başlatılır;
- her sınıf türünün statik olmayan veri üyesi ve tüm taban sınıfı alt nesneleri bir constexpr oluşturucusuna sahip

## <a name="init_list_constructors"></a> Başlatıcı listesi oluşturucular

Bir oluşturucu uzun sürerse bir [std::initializer_list\<T\> ](../standard-library/initializer-list-class.md) parametresinin ve herhangi bir parametre varsayılan bağımsız değişkenlere sahip gibi sınıfı olduğunda, kurucu aşırı yükleme çözünürlüğü içinde seçilir doğrudan başlatma örneği. İnitializer_list kabul edebilen herhangi bir üyesi başlatmak için kullanabilirsiniz. Örneğin, Box sınıfı (daha önce gösterilen) olduğunu varsayalım bir `std::vector<string>` üye `m_contents`. Böyle bir oluşturucu sağlayabilirsiniz:

```cpp
    Box(initializer_list<string> list, int w = 0, int h = 0, int l = 0)
        : m_contents(list), m_width(w), m_height(h), m_length(l)
{}
```

' İ tıklatın ve ardından kutusu nesneleri şöyle oluşturun:

```cpp
    Box b{ "apples", "oranges", "pears" }; // or ...
    Box b2(initializer_list<string> { "bread", "cheese", "wine" }, 2, 4, 6);
```

## <a name="explicit_constructors"></a> Açık oluşturucular

Bir sınıfın tek bir parametreye sahip bir oluşturucusu varsa veya biri dışındaki tüm parametreler varsayılan bir değer varsa, parametre türü örtülü olarak sınıf türüne dönüştürülebilir. Örneğin, varsa `Box` sınıfı böyle bir oluşturucu vardır:

```cpp
Box(int size): m_width(size), m_length(size), m_height(size){}
```

Böyle bir kutu başlatmak mümkündür:

```cpp
Box b = 42;
```

Veya bir kutu alan bir işlev için bir int geçirin:

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

Bu tür dönüştürmeler bazı durumlarda yararlı olabilir, ancak daha sık küçük ancak önemli hataları kodunuzda açabilir. Genel kural olarak, kullanmalısınız **açık** anahtar sözcüğü bu tür bir örtük tür dönüştürme önlemek için bir oluşturucu (ve kullanıcı tanımlı işleçler):

```cpp
explicit Box(int size): m_width(size), m_length(size), m_height(size){}
```

Bu satır, oluşturucu açık olduğunda, bir derleyici hatasına neden olur: `ShippingOrder so(42, 10.8);`.  Daha fazla bilgi için [kullanıcı tanımlı tür dönüşümleri](../cpp/user-defined-type-conversions-cpp.md).

## <a name="order_of_construction"></a> Oluşturma sırası

Bir oluşturucu kendi işini şu sırayla gerçekleştirir:

1. Temel sınıfı ve üye oluşturucuları bildirim sırasına göre çağırır.

1. Sınıf sanal temel sınıflardan türetilmişse, nesnenin sanal taban işaretçilerini başlatır.

1. Sınıf sanal işlevler içeriyorsa ya da devralıyorsa, nesnenin sanal işlev işaretçilerini başlatır. Sanal işlev işaretçileri, sanal işlev çağrılarının koda doğru bağlanmasını sağlamak için sınıfın sanal işlev tablosunu gösterir.

1. Kendi işlev gövdesindeki tüm kodları yürütür.

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

```Output
Contained1 ctor
Contained2 ctor
BaseContainer ctor
Contained3 ctor
DerivedContainer ctor
```

Bir türetilmiş sınıf oluşturucusu her zaman bir taban sınıf oluşturucusunu çağırır, böylece bu sınıf ek bir çalışma yapılmadan önce tümüyle oluşturulmuş taban sınıflarına dayanabilir. Temel sınıf oluşturucuları türetme sırayla çağrılır — Örneğin, varsa `ClassA` türetilir `ClassB`, türetilen `ClassC`, `ClassC` Oluşturucusu önce çağrılır sonra `ClassB` oluşturucusu, ardından `ClassA` Oluşturucusu.

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

### <a name="constructors-for-classes-that-have-multiple-inheritance"></a>Birden çok kalıtıma sahip sınıfların oluşturucuları

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

```Output
BaseClass1 ctor
BaseClass2 ctor
BaseClass3 ctor
DerivedClass ctor
```

## <a name="virtual_functions_in_constructors"></a> Oluşturucularda sanal işlevler

Oluşturucularda sanal işlevleri çağırırken dikkatli olmanız önerilir. Temel sınıf oluşturucusu her zaman türetilen sınıf oluşturucusundan önce çağrıldığından, temel oluşturucu içinde çağrılan işlev türetilen sınıf sürümü değil, temel sınıf sürümüdür. Aşağıdaki örnekte, oluşturma bir `DerivedClass` neden `BaseClass` uygulaması `print_it()` önce yürütülecek `DerivedClass` Oluşturucusu nedenleri `DerivedClass` uygulaması `print_it()` yürütmek için:

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

```Output
BaseClass print_it
Derived Class print_it
```

## <a name="delegating_constructors"></a> Oluşturucuları temsilci olarak görevlendirme

A *temsilci Oluşturucu* başlatma işinin bir kısmını yapmak için aynı sınıf içinde farklı bir oluşturucu çağırır. Birden çok Oluşturucu tüm benzer işi gerçekleştirmek sahip olduğunda bu kullanışlıdır. Ana mantıksal bir oluşturucuda yazabilir ve diğerlerinden çağırır. Aşağıdaki basit örnekte, kendi iş Box(int,int,int) Box(int) atar:

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

Herhangi bir oluşturucunun işi biter bitmez, oluşturucular tarafından oluşturulan nesne tamamen başlatılır. Daha fazla bilgi için [tek düzen başlatma ve oluşturucuları temsilci olarak görevlendirme](../cpp/uniform-initialization-and-delegating-constructors.md).

## <a name="inheriting_constructors"></a> Devralma oluşturucular (C ++ 11)

Türetilmiş bir sınıf kullanarak oluşturucular doğrudan temel sınıftan devralıp bir **kullanarak** aşağıdaki örnekte gösterildiği gibi bildirimi:

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

**Visual Studio 2017 sürüm 15.7 ve üzeri**: **kullanarak** deyiminde **/Std: c ++ 17** modu, tüm oluşturucular dışında aynı imzaya sahip bir temel sınıftan kapsamına getirir türetilmiş sınıf oluşturucular için. Genel olarak, devralma oluşturucuları türetilen sınıfın yeni hiçbir veri üyeleri bildirir olduğunda veya oluşturucuları kullanmak en iyisidir. Ayrıca bkz: [Visual Studio 2017 sürüm 15.7 geliştirmeleri](../cpp-conformance-improvements-2017.md#improvements_157).

Bu tür bir temel sınıf belirtiyorsa bir sınıf şablonunun tür bağımsız değişkeninden tüm oluşturucuları devralabilir:

```cpp
template< typename T >
class Derived : T {
    using T::T;   // declare the constructors from T
    // ...
};
```

Bu temel sınıfların aynı imzaya sahip oluşturucuları varsa birden çok temel sınıftan türetilen bir sınıf devralınamaz.

## <a name="constructors_in_composite_classes"></a> Oluşturucular ve bileşik sınıflar

Sınıf türü üyeleri içeren sınıflar olarak bilinir *bileşik sınıflar*. Bileşik bir sınıfın sınıf türünde bir üyesi oluşturulduğunda, sınıfın kendisi çağrılmadan önce oluşturucu çağrılır. İçerilen bir sınıfın varsayılan bir oluşturucusu yoksa, bileşik sınıfın oluşturucusunda bir başlatma listesi kullanmalısınız. Önceki `StorageBox` türünü değiştirirseniz örnek `m_label` yeni bir üye değişkeni `Label` sınıfı, temel sınıf oluşturucusunu çağırın ve gerekir başlatmak `m_label` değişkeninde `StorageBox` Oluşturucusu:

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
