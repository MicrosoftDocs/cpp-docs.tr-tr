---
title: Oluşturucular (C++)
ms.date: 12/27/2019
helpviewer_keywords:
- constructors [C++]
- objects [C++], creating
- instance constructors
ms.assetid: 3e9f7211-313a-4a92-9584-337452e061a9
ms.openlocfilehash: 4640bcf5f21bbe018a8744a6c5206bdd09509c98
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749651"
---
# <a name="constructors-c"></a>Oluşturucular (C++)

Sınıf üyelerinin nasıl başlatıldığını özelleştirmek veya sınıfınızın bir nesnesi oluşturulduğunda işlevleri çağırmak için bir *oluşturucu*tanımlayın. Bir oluşturucu sınıfla aynı ada sahiptir ve geri dönüş değeri yoktur. Başlatmayı çeşitli şekillerde özelleştirmek için gerektiğinde çok sayıda aşırı yüklü oluşturucu tanımlayabilirsiniz. Genellikle, oluşturucular ortak erişilebilirlik böylece sınıf tanımı veya devralma hiyerarşisi dışında kod sınıfın nesneleri oluşturabilirsiniz var. Ama aynı zamanda **korumalı** veya **özel**olarak bir yapıcı ilan edebilirsiniz.

Yapıcılar isteğe bağlı olarak bir üye giriş listesi alabilir. Bu, sınıf üyelerini başlatmanın, oluşturucu gövdeye değer atamaktan daha etkili bir yoludur. Aşağıdaki örnekte, `Box` üç aşırı yüklü oluşturucusu olan bir sınıf gösterilmektedir. Son iki kullanım üye init listeleri:

```cpp
class Box {
public:
    // Default constructor
    Box() {}

    // Initialize a Box with equal dimensions (i.e. a cube)
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

Bir sınıfın örneğini bildirdiğinizde, derleyici aşırı yük çözümleme kurallarına göre hangi oluşturucuyu çağıracak seçecektir:

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

- Yapıcılar satır satır **olarak**ilan edilebilir , [açık](#explicit_constructors), **arkadaş** veya [constexpr](#constexpr_constructors).
- Bir oluşturucu **const,** **uçucu** veya **const uçucu**olarak bildirilen bir nesneyi başlatma. Nesne, oluşturucu tamamlandıktan sonra **const** olur.
- Bir uygulama dosyasında bir oluşturucu tanımlamak için, diğer üye işlevlerde olduğu gibi ona nitelikli bir ad verin: `Box::Box(){...}`.

## <a name="member-initializer-lists"></a><a name="member_init_list"></a>Üye başlatma listeleri

Bir oluşturucu isteğe bağlı olarak, oluşturucu gövdenin yürütülmesinden önce sınıf üyelerini ilk olarak alan bir üye başlatma listesine sahip olabilir. (Üye baş harflistesinin, std türündeki *bir baş harf listesiyle* aynı şey olmadığını [\<unutmayın::initializer_list T>](../standard-library/initializer-list-class.md).)

Üye nin baş harflerini kullanmak, üyeyi doğrudan başharfe ayırdığı için oluşturucunun gövdesindeki değerleri atamaktan çok tercih edilir. Aşağıdaki örnekte üye baş harflistesi iki nokta üst üste sonra tüm **tanımlayıcı (bağımsız değişken)** ifadeler oluşur gösterir:

```cpp
    Box(int width, int length, int height)
        : m_width(width), m_length(length), m_height(height)
    {}
```

Tanımlayıcı bir sınıf üyesine başvurmalıdır; bağımsız değişkenin değeri ile başharfe işlenir. Bağımsız değişken, oluşturucu parametrelerden, bir işlev çağrısından veya [std::initializer_list\<T>. ](../standard-library/initializer-list-class.md)

**const** üyeleri ve referans türü üyeleri üye initializer listesinde baş harfe getirilmelidir.

Parametreli taban sınıf oluşturuculara çağrılar, türemiş oluşturucunun yürütülmesinden önce taban sınıfın tam olarak başlatılmasını sağlamak için başharf listesinde yapılmalıdır.

## <a name="default-constructors"></a><a name="default_constructors"></a>Varsayılan oluşturucular

*Varsayılan oluşturucuların* genellikle parametreleri yoktur, ancak varsayılan değerlere sahip parametrelere sahip olabilirler.

```cpp
class Box {
public:
    Box() { /*perform any required default initialization steps*/}

    // All params have default values
    Box (int w = 1, int l = 1, int h = 1): m_width(w), m_height(h), m_length(l){}
...
}
```

Varsayılan yapıcılar [özel üye işlevlerden](special-member-functions.md)biridir. Bir sınıfta hiçbir oluşturucu bildirilmemişse, derleyici örtülü bir **satır içinde** varsayılan oluşturucu sağlar.

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

Örtük bir varsayılan oluşturucuya güveniyorsanız, önceki örnekte gösterildiği gibi, sınıf tanımındaki üyeleri başharfe aldığınızdan emin olun. Bu baş harfler olmadan, üyeler fönsüz olur ve Volume() çağrısı bir çöp değeri üretir. Genel olarak, örtük bir varsayılan oluşturucuya güvenmemese bile üyeleri bu şekilde başlatmaiyi iyi bir uygulamadır.

Derleyicinin [silinmiş](#explicitly_defaulted_and_deleted_constructors)olarak tanımlayarak örtülü varsayılan bir oluşturucu oluşturmasını engelleyebilirsiniz:

```cpp
    // Default constructor
    Box() = delete;
```

Derleyici tarafından oluşturulan varsayılan oluşturucu, herhangi bir sınıf üyesi varsayılan olarak oluşturulabilir değilse silinmiş olarak tanımlanır. Örneğin, sınıf türütüm üyeleri ve sınıf türü üyeleri, erişilebilir bir varsayılan oluşturucu ve yıkıcılar olmalıdır. Başvuru türünün tüm veri üyelerinin yanı sıra **const** üyelerin varsayılan bir üye başlatmacısı olmalıdır.

Derleyici tarafından oluşturulan varsayılan oluşturucuçağırıp parantez kullanmaya çalıştığınızda bir uyarı verilir:

```cpp
class myclass{};
int main(){
myclass mc();     // warning C4930: prototyped function not called (was a variable definition intended?)
}
```

Bu, En Çok Güçlük Çıkaran Ayrıştırma sorununa bir örnektir. Örnek ifade bir işlevin bildirimi ya da varsayılan bir oluşturucunun çağrılması olarak yorumlanabileceğinden ve C++ ayrıştırıcıları diğer şeylere oranla bildirimlere öncelik verdiğinden, ifade bir işlev bildirimi olarak ele alınır. Daha fazla bilgi [için, En Vexing Parse](https://en.wikipedia.org/wiki/Most_vexing_parse)bakın.

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

Ancak, bir dizi Kutu nesnesini başlatmak için bir tür baş harf listesi kullanabilirsiniz:

```cpp
Box boxes[3]{ { 1, 2, 3 }, { 4, 5, 6 }, { 7, 8, 9 } };
```

Daha fazla bilgi için [Initializers'a](initializers.md)bakın.

## <a name="copy-constructors"></a><a name="copy_and_move_constructors"></a>Kopya yapıcılar

Bir *kopya oluşturucu,* üye değerleri aynı türden bir nesneden kopyalayarak nesneyi başlatılmasını sağlar. Sınıf üyeleriniz skaler değerler gibi tüm basit türlerse, derleyici tarafından oluşturulan kopya oluşturucu yeterlidir ve kendi verilerinizi tanımlamanız gerekmez. Sınıfınız daha karmaşık bir başlatma gerektiriyorsa, özel bir kopya oluşturucu uygulamanız gerekir. Örneğin, bir sınıf üyesi bir işaretçiise, yeni bellek ayırmak ve değerleri diğerinin işaretli nesnesinden kopyalamak için bir kopya oluşturucu tanımlamanız gerekir. Derleyici tarafından oluşturulan kopya oluşturucu, yeni işaretçi hala diğerinin bellek konumunu işaret eder, böylece işaretçikopyalar.

Bir kopya oluşturucu bu imzalardan birine sahip olabilir:

```cpp
    Box(Box& other); // Avoid if possible--allows modification of other.
    Box(const Box& other);
    Box(volatile Box& other);
    Box(volatile const Box& other);

    // Additional parameters OK if they have default values
    Box(Box& other, int i = 42, string label = "Box");
```

Bir kopya oluşturucu tanımladığınızda, bir kopya atama işleci (=) de tanımlamalısınız. Daha fazla bilgi için [Copy constructors and copy assignment operators](copy-constructors-and-copy-assignment-operators-cpp.md) [bkz.](assignment.md)

Kopya oluşturucuyu silinmiş olarak tanımlayarak nesnenizin kopyalanmasını engelleyebilirsiniz:

```cpp
    Box (const Box& other) = delete;
```

Nesneyi kopyalamaya çalışmak *C2280 hatası üretir: silinmiş bir işleve başvurmaya çalışmak.*

## <a name="move-constructors"></a><a name="move_constructors"></a>Konstrüktörleri taşı

*Hareket oluşturucu,* varolan bir nesnenin verilerinin sahipliğini özgün verileri kopyalamadan yeni bir değişkene taşıyan özel bir üye işlevdir. İlk parametresi olarak bir rvalue başvurusu alır ve ek parametrelervarsayılan değerlere sahip olmalıdır. Taşı oluşturucular, büyük nesnelerin etrafından geçerken programınızın verimliliğini önemli ölçüde artırabilir.

```cpp
Box(Box&& other);
```

Derleyici, nesnenin yok olmak üzere olan ve artık kaynaklarına ihtiyaç damayacak aynı türden başka bir nesne tarafından başlatılması olan belirli durumlarda bir hareket oluşturucuseçer. Aşağıdaki örnekte, bir hareket oluşturucu aşırı yük çözünürlüğü tarafından seçildiğinde bir durum gösterilmektedir. Çağıran `get_Box()`yapı oluşturucuda, döndürülen değer bir *xvalue* (eXpiring value) değeridir. Herhangi bir değişkene atanmadı ve bu nedenle kapsam dışına çıkmak üzeredir. Bu örnek için motivasyon sağlamak için, Kutu'ya içeriğini temsil eden büyük bir dizeleri vektörü verelim. Hareket oluşturucu, vektörü ve dizeleri kopyalamak yerine, vektörün artık yeni nesneye ait olması için onu son kullanma değeri "kutusu"ndan "çalar". Çağrı, `std::move` hem hem de `vector` `string` sınıfların kendi hareket yapıcılarını uyguladığı için gereken tek şeydir.

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
    void Print_Contents()
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
    b2.Print_Contents(); // Prove that we have all the values

    char ch;
    cin >> ch; // keep window open
    return 0;
}
```

Bir sınıf bir hareket oluşturucu tanımlamazsa, derleyici kullanıcı tarafından beyan edilen kopya oluşturucu, kopya atama işleci, taşıma atama işleci veya yıkıcı yoksa örtülü bir tane oluşturur. Açık veya örtülü hareket oluşturucu tanımlanmamışsa, aksi takdirde bir hareket oluşturucusu kullanacak işlemler kopya oluşturucuyu kullanır. Bir sınıf bir hareket oluşturucu veya taşıma atama işleci bildirirse, örtülü olarak bildirilen kopya oluşturucu silinmiş olarak tanımlanır.

Sınıf türleri olan herhangi bir üyenin yıkıcısı yoksa veya derleyici taşıma işlemi için hangi yapıyı kullanacağını belirleyemiyorsa, örtülü olarak bildirilen bir hareket oluşturucu silinmiş olarak tanımlanır.

Önemsiz olmayan bir hareket oluşturucusu nasıl yazılabilen hakkında daha fazla bilgi için [bkz.](../cpp/move-constructors-and-move-assignment-operators-cpp.md)

## <a name="explicitly-defaulted-and-deleted-constructors"></a><a name="explicitly_defaulted_and_deleted_constructors"></a>Açıkça varsayılan ve silinen yapıcılar

Kopya oluşturucuları, varsayılan oluşturucuları, taşı oluşturucuları, kopya atama işleçlerini, atama işleçlerini ve yıkıcıları açıkça *varsayılan olarak varsayılan* olarak oluşturabilirsiniz. Tüm özel üye işlevleri açıkça *silebilirsiniz.*

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

Daha fazla bilgi için, [açıkça varsayılan ve silinmiş işlevler](../cpp/explicitly-defaulted-and-deleted-functions.md)bakın.

## <a name="constexpr-constructors"></a><a name="constexpr_constructors"></a>constexpr yapıcılar

Bir yapıcı [constexpr](constexpr-cpp.md) olarak ilan edilebilir eğer

- ya temerrüde düşürür ya da genel olarak [constexpr fonksiyonları](constexpr-cpp.md#constexpr_functions) için tüm koşulları karşılar;
- sınıfın sanal taban sınıfları yoktur;
- parametrelerin her biri [bir edebi türüdür;](trivial-standard-layout-and-pod-types.md#literal_types)
- vücut bir fonksiyon try-blok değildir;
- tüm statik olmayan veri üyeleri ve taban sınıf alt nesneleri baş harfe çevrilir;
- sınıf (a) varyant üyeleri olan bir sendika ysa veya (b) anonim sendikaları varsa, sendika üyelerinden yalnızca biri baş harfe çevrilir;
- sınıf türündeki her statik olmayan veri üyesi ve tüm taban sınıf alt nesnelerin bir constexpr oluşturucusu vardır

## <a name="initializer-list-constructors"></a><a name="init_list_constructors"></a>Baş harfliste oluşturucuları

Bir oluşturucu bir [std\<alırsa::initializer_list T\> ](../standard-library/initializer-list-class.md) parametresi olarak ve diğer parametrelervarsayılan bağımsız değişkenlere sahipse, sınıf doğrudan başlatma yoluyla anında olduğunda bu kurucu aşırı yük çözümünde seçilecektir. Initializer_list, kabul edebilirsiniz herhangi bir üye nin başlatılması nı kullanabilirsiniz. Örneğin, Kutu sınıfının (daha önce gösterildiği) bir `std::vector<string>` üyesi `m_contents`olduğunu varsayalım. Bunun gibi bir oluşturucu sağlayabilirsiniz:

```cpp
    Box(initializer_list<string> list, int w = 0, int h = 0, int l = 0)
        : m_contents(list), m_width(w), m_height(h), m_length(l)
{}
```

Ve sonra kutu nesneleri gibi oluşturun:

```cpp
    Box b{ "apples", "oranges", "pears" }; // or ...
    Box b2(initializer_list<string> { "bread", "cheese", "wine" }, 2, 4, 6);
```

## <a name="explicit-constructors"></a><a name="explicit_constructors"></a>Açık yapıcılar

Bir sınıfın tek bir parametresi olan bir oluşturucusu varsa veya biri dışındaki tüm parametreler varsayılan değere sahipse, parametre türü örtülü olarak sınıf türüne dönüştürülebilir. Örneğin, `Box` sınıfın şu gibi bir oluşturucusu varsa:

```cpp
Box(int size): m_width(size), m_length(size), m_height(size){}
```

Bir Kutuyu şu şekilde başlatmak mümkündür:

```cpp
Box b = 42;
```

Veya kutu alan bir işlev için bir int geçirin:

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

Bu tür dönüşümler bazı durumlarda yararlı olabilir, ancak daha sık kodunuzda ince ama ciddi hatalara yol açabilir. Genel bir kural olarak, bu tür örtük tür dönüştürmeyi önlemek için bir oluşturucu (ve kullanıcı tanımlı işleçler) üzerinde **açık** anahtar kelime kullanmanız gerekir:

```cpp
explicit Box(int size): m_width(size), m_length(size), m_height(size){}
```

Oluşturucu açık olduğunda, bu satır derleyici `ShippingOrder so(42, 10.8);`hatasına neden olur: .  Daha fazla bilgi için [Bkz. Kullanıcı Tanımlı Tür Dönüşümleri.](../cpp/user-defined-type-conversions-cpp.md)

## <a name="order-of-construction"></a><a name="order_of_construction"></a>İnşaat nişanı

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

Bir türetilmiş sınıf oluşturucusu her zaman bir taban sınıf oluşturucusunu çağırır, böylece bu sınıf ek bir çalışma yapılmadan önce tümüyle oluşturulmuş taban sınıflarına dayanabilir. Taban sınıf oluşturucular türetme sırasına göre çağrılır—örneğin, `ClassA` `ClassB` `ClassC`türetilmişse, `ClassC` yani, önce `ClassB` yapıcı, sonra `ClassA` yapıcı denir.

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

## <a name="derived-constructors-and-extended-aggregate-initialization"></a><a name="extended_aggregate"></a>Türemiş yapıcılar ve genişletilmiş toplam başlatma

Bir taban sınıfın oluşturucusu ortak değil, ancak türetilmiş bir sınıf için erişilebilirse, Visual Studio 2017'de **/std:c++17** modu altında ve daha sonra türemiş türdeki bir nesneyi başlatmak için boş ayraçlar kullanamazsınız.

Aşağıdaki örnek, C++14 konforman davranışını gösterir:

```cpp
struct Derived;

struct Base {
    friend struct Derived;
private:
    Base() {}
};

struct Derived : Base {};

Derived d1; // OK. No aggregate init involved.
Derived d2 {}; // OK in C++14: Calls Derived::Derived()
               // which can call Base ctor.
```

C++17'de `Derived` artık toplam bir tür olarak kabul edilir. Bu, genişletilmiş toplam `Base` başlatma kuralının bir parçası olarak, özel varsayılan oluşturucu aracılığıyla başlatılmasının doğrudan gerçekleştiği anlamına gelir. Daha önce, `Base` özel yapıcı `Derived` yapıcı aracılığıyla çağrıldı ve arkadaş bildirimi nedeniyle başarılı oldu.

Aşağıdaki örnek, Visual Studio 2017'de ve daha sonra **/std:c++17** modunda C++17 davranışını gösterir:

```cpp
struct Derived;

struct Base {
    friend struct Derived;
private:
    Base() {}
};

struct Derived : Base {
    Derived() {} // add user-defined constructor
                 // to call with {} initialization
};

Derived d1; // OK. No aggregate init involved.

Derived d2 {}; // error C2248: 'Base::Base': cannot access
               // private member declared in class 'Base'
```

### <a name="constructors-for-classes-that-have-multiple-inheritance"></a>Birden çok kalıtıma sahip sınıflar için kurucular

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

## <a name="delegating-constructors"></a><a name="delegating_constructors"></a>Yapıcıları ata

*Bir delegating oluşturucu,* başlatma çalışmalarının bazılarını yapmak için aynı sınıftafarklı bir oluşturucu çağırır. Bu, tüm benzer işi gerçekleştirmek zorunda birden çok oluşturucuvarsa yararlıdır. Ana mantığı bir oluşturucuya yazıp başkalarından çağırabilirsiniz. Aşağıdaki önemsiz örnekte, Box(int) çalışmalarını Box'a (int,int,int) delege eder:

```cpp
class Box {
public:
    // Default constructor
    Box() {}

    // Initialize a Box with equal dimensions (i.e. a cube)
    Box(int i) :  Box(i, i, i);  // delegating constructor
    {}

    // Initialize a Box with custom dimensions
    Box(int width, int length, int height)
        : m_width(width), m_length(length), m_height(height)
    {}
    //... rest of class as before
};
```

Herhangi bir oluşturucunun işi biter bitmez, oluşturucular tarafından oluşturulan nesne tamamen başlatılır. Daha fazla bilgi için bkz: [Delegating Constructors.](../cpp/delegating-constructors.md)

## <a name="inheriting-constructors-c11"></a><a name="inheriting_constructors"></a>Kurucuların devrallanması (C++11)

Türetilen bir sınıf, aşağıdaki örnekte gösterildiği gibi **bir kullanma** bildirimi kullanarak doğrudan taban sınıftan yapıcıları devralabilir:

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

::: moniker range=">=vs-2017"

**Visual Studio 2017 ve sonrası**: **/std:c++17** **modundaki kullanım** deyimi, türemiş sınıftaki kurucular için aynı imzaya sahip olanlar hariç, taban sınıftaki tüm yapıcıları kapsama getirir. Genel olarak, türemiş sınıf yeni veri üyeleri veya oluşturucular beyan ettiğinde devralan yapıcılar kullanmak en iyisidir. Ayrıca Visual [Studio 2017 sürüm 15.7 gelişmeler](https://docs.microsoft.com/cpp/overview/cpp-conformance-improvements?view=vs-2017#improvements_157)e bakınız.

::: moniker-end

Bir sınıf şablonu, bu tür bir taban sınıf belirtirse, bir tür bağımsız değişkeninden tüm oluşturucuları devralabilir:

```cpp
template< typename T >
class Derived : T {
    using T::T;   // declare the constructors from T
    // ...
};
```

Bu temel sınıfların aynı imzaya sahip oluşturucuları varsa, türeyen bir sınıf birden çok temel sınıftan devralamaz.

## <a name="constructors-and-composite-classes"></a><a name="constructors_in_composite_classes"></a>Yapıcılar ve bileşik sınıflar

Sınıf türü üyeleri içeren sınıflar *bileşik sınıflar*olarak bilinir. Bileşik bir sınıfın sınıf türünde bir üyesi oluşturulduğunda, sınıfın kendisi çağrılmadan önce oluşturucu çağrılır. İçerilen bir sınıfın varsayılan bir oluşturucusu yoksa, bileşik sınıfın oluşturucusunda bir başlatma listesi kullanmalısınız. `StorageBox` Önceki örnekte, `m_label` üye değişkenin türünü yeni `Label` bir sınıfa değiştirirseniz, hem taban sınıf oluşturucuyu çağırmanız hem de `m_label` `StorageBox` oluşturucudaki değişkeni başlatmanız gerekir:

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

## <a name="in-this-section"></a>Bu bölümde

- [Kopya yapıcılar ve kopyalama atama işleçleri](copy-constructors-and-copy-assignment-operators-cpp.md)
- [Oluşturucuları ve taşıma atama işleçlerini taşıyın](move-constructors-and-move-assignment-operators-cpp.md)
- [Yapıcıları ata](delegating-constructors.md)

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve structs](classes-and-structs-cpp.md)
