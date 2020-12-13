---
description: ': Oluşturucular hakkında daha fazla bilgi edinin (C++)'
title: Oluşturucular (C++)
ms.date: 12/27/2019
helpviewer_keywords:
- constructors [C++]
- objects [C++], creating
- instance constructors
ms.assetid: 3e9f7211-313a-4a92-9584-337452e061a9
ms.openlocfilehash: bd93053d63e76aef9f2284e18f7748334a3fc6ce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344633"
---
# <a name="constructors-c"></a>Oluşturucular (C++)

Sınıf üyelerinin nasıl başlatıldığını özelleştirmek veya sınıfınızın bir nesnesi oluşturulduğunda işlevleri çağırmak için bir *Oluşturucu* tanımlayın. Bir Oluşturucu, sınıfla aynı ada sahip ve dönüş değeri yok. Başlatmayı çeşitli yollarla özelleştirmek için gereken sayıda aşırı yüklenmiş Oluşturucu tanımlayabilirsiniz. Genellikle, oluşturucular, sınıf tanımı veya devralma hiyerarşisi dışındaki kodların sınıfın nesnelerini oluşturabilmesi için genel erişilebilirliği vardır. Ancak, veya olarak bir Oluşturucu da bildirebilirsiniz **`protected`** **`private`** .

Oluşturucular, isteğe bağlı olarak bir üye init listesi alabilir. Bu, Oluşturucu gövdesinde değer atamaya kıyasla sınıf üyelerini başlatmanın daha verimli bir yoludur. Aşağıdaki örnekte, `Box` üç aşırı yüklü Oluşturucu içeren bir sınıf gösterilmektedir. Son iki kullanılan üye başlangıç listeleri:

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

Bir sınıfın örneğini bildirdiğinizde, derleyici, yeniden yükleme çözümünün kurallarına göre hangi oluşturucuyu çağıracağına seçer:

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

- Oluşturucular **`inline`** , [Açık](#explicit_constructors) **`friend`** veya [constexpr](#constexpr_constructors)olarak tanımlanmış olabilir.
- Bir Oluşturucu, veya olarak belirtilen bir nesneyi başlatabilir **`const`** **`volatile`** **`const volatile`** . Nesne, **`const`** Oluşturucu tamamlandıktan sonra olur.
- Bir uygulama dosyasında bir Oluşturucu tanımlamak için, başka bir üye işlevi ile olduğu gibi tam adı verin: `Box::Box(){...}` .

## <a name="member-initializer-lists"></a><a name="member_init_list"></a> Üye başlatıcı listeleri

Oluşturucu, isteğe bağlı olarak, Oluşturucu gövdesinin yürütülmesinden önce sınıf üyelerini Başlatan bir üye Başlatıcı listesine sahip olabilir. (Üye başlatıcısı listesinin [std:: initializer_list \<T>](../standard-library/initializer-list-class.md)türünde bir *Başlatıcı listesiyle* aynı şey olmadığına unutmayın.)

Üyeyi doğrudan başlattığında, üye başlatıcısı listesinin kullanılması, oluşturucunun gövdesinde değer atamaya tercih edilir. Aşağıdaki örnekte, üye Başlatıcı listesi, iki nokta üst üste gelen tüm **tanımlayıcı (bağımsız değişken)** ifadelerinden oluşur:

```cpp
    Box(int width, int length, int height)
        : m_width(width), m_length(length), m_height(height)
    {}
```

Tanımlayıcı bir sınıf üyesine başvurmalıdır; bağımsız değişkeninin değeri ile başlatılır. Bağımsız değişken, Oluşturucu parametrelerinden biri, bir işlev çağrısı veya [std:: initializer_list \<T> ](../standard-library/initializer-list-class.md)olabilir.

**`const`** üye Başlatıcı listesinde, başvuru türünün üyeleri ve üyeleri başlatılmalıdır.

Türetilmiş oluşturucunun yürütülmesi öncesinde temel sınıfın tamamen başlatılmış olduğundan emin olmak için, Oluşturucu listesinde parametreli temel sınıf oluşturuculara çağrılar yapılmalıdır.

## <a name="default-constructors"></a><a name="default_constructors"></a> Varsayılan oluşturucular

*Varsayılan oluşturucuların* genellikle parametresi yoktur, ancak varsayılan değerlere sahip parametrelere sahip olabilirler.

```cpp
class Box {
public:
    Box() { /*perform any required default initialization steps*/}

    // All params have default values
    Box (int w = 1, int l = 1, int h = 1): m_width(w), m_height(h), m_length(l){}
...
}
```

Varsayılan oluşturucular [özel üye işlevlerinden](special-member-functions.md)biridir. Bir sınıf içinde hiçbir Oluşturucu bildirilirse, derleyici örtük bir **`inline`** Varsayılan Oluşturucu sağlar.

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

Örtük bir varsayılan oluşturucuya güveniyorsanız, önceki örnekte gösterildiği gibi, sınıf tanımındaki üyeleri başlattığınızdan emin olun. Bu başlatıcılar olmadan, Üyeler başlatılmamış olur ve Volume () çağrısı bir çöp değeri oluşturur. Genel olarak, örtük bir varsayılan oluşturucuya bağlı olmasa bile üyeleri bu şekilde başlatmak iyi bir uygulamadır.

Derleyicinin [Silinmiş](#explicitly_defaulted_and_deleted_constructors)olarak tanımlayarak örtük bir varsayılan Oluşturucu oluşturmasını engelleyebilirsiniz:

```cpp
    // Default constructor
    Box() = delete;
```

Derleyici tarafından oluşturulan varsayılan Oluşturucu, herhangi bir sınıf üyesi varsayılan olarak oluşturulabilir değilse, silindi olarak tanımlanır. Örneğin, sınıf türündeki tüm Üyeler ve sınıf türü üyeleri, erişilebilen bir varsayılan oluşturucuya ve yıkıcıya sahip olmalıdır. Başvuru türünün tüm veri üyelerinin yanı sıra **`const`** üyelerin bir varsayılan üye başlatıcısı olması gerekir.

Derleyicinin ürettiği varsayılan oluşturucuyu çağırdığınızda ve parantez kullanmaya çalıştığınızda bir uyarı verilir:

```cpp
class myclass{};
int main(){
myclass mc();     // warning C4930: prototyped function not called (was a variable definition intended?)
}
```

Bu, En Çok Güçlük Çıkaran Ayrıştırma sorununa bir örnektir. Örnek ifade bir işlevin bildirimi ya da varsayılan bir oluşturucunun çağrılması olarak yorumlanabileceğinden ve C++ ayrıştırıcıları diğer şeylere oranla bildirimlere öncelik verdiğinden, ifade bir işlev bildirimi olarak ele alınır. Daha fazla bilgi için bkz. [en çok tümleştirme ayrıştırma](https://en.wikipedia.org/wiki/Most_vexing_parse).

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

Ancak, Box nesnelerinin bir dizisini başlatmak için bir başlatıcı listeleri kümesi kullanabilirsiniz:

```cpp
Box boxes[3]{ { 1, 2, 3 }, { 4, 5, 6 }, { 7, 8, 9 } };
```

Daha fazla bilgi için bkz. [başlatıcılar](initializers.md).

## <a name="copy-constructors"></a><a name="copy_and_move_constructors"></a> Kopya oluşturucular

Bir *kopya Oluşturucu* , üye değerlerini aynı türdeki bir nesneden kopyalayarak bir nesneyi başlatır. Sınıf üyeleriniz skaler değerler gibi basit türlerdir, derleyici tarafından oluşturulan kopya Oluşturucu yeterlidir ve kendinizinkini tanımlamanız gerekmez. Sınıfınız daha karmaşık başlatma gerektiriyorsa, özel bir kopya Oluşturucu uygulamanız gerekir. Örneğin, bir sınıf üyesi bir işaretçisiyse, yeni bellek ayırmak için bir kopya Oluşturucu tanımlamanız ve değerleri diğerinin işaret eden nesnesinden kopyalamanız gerekir. Derleyici tarafından oluşturulan kopya Oluşturucu, yeni işaretçinin hala diğer bellek konumunu işaret ettiği şekilde işaretçiyi kopyalar.

Kopya Oluşturucu şu imzalardan birine sahip olabilir:

```cpp
    Box(Box& other); // Avoid if possible--allows modification of other.
    Box(const Box& other);
    Box(volatile Box& other);
    Box(volatile const Box& other);

    // Additional parameters OK if they have default values
    Box(Box& other, int i = 42, string label = "Box");
```

Bir kopya Oluşturucu tanımladığınızda, bir kopya atama işleci (=) de tanımlamanız gerekir. Daha fazla bilgi için bkz. [atama](assignment.md) ve [kopya oluşturucuları ve kopya atama işleçleri](copy-constructors-and-copy-assignment-operators-cpp.md).

Kopya oluşturucuyu silinmiş olarak tanımlayarak, nesnenizin kopyalanmasını engelleyebilirsiniz:

```cpp
    Box (const Box& other) = delete;
```

Nesneyi kopyalamaya çalışmak C2280 hatasını üretir *: silinen bir işleve başvurulmaya çalışılıyor*.

## <a name="move-constructors"></a><a name="move_constructors"></a> Taşıma Oluşturucuları

*Taşıma oluşturucusu* , varolan bir nesne verisinin sahipliğini özgün verileri kopyalamadan yeni bir değişkene taşır özel bir üye işlevidir. İlk parametresi olarak bir rvalue başvurusu alır ve tüm ek parametreler varsayılan değerlere sahip olmalıdır. Taşıma Oluşturucuları, büyük nesneler etrafında geçiş yaparken programınızın verimliliğini önemli ölçüde artırabilir.

```cpp
Box(Box&& other);
```

Derleyici, nesnenin yok edileceği ve artık kaynaklarına ihtiyacı olmayan aynı türde başka bir nesne tarafından başlatıldığı bazı durumlarda bir taşıma Oluşturucusu seçer. Aşağıdaki örnekte, bir taşıma Oluşturucusu aşırı yükleme çözümlemesi tarafından seçildiğinde bir durum gösterilmektedir. Çağıran oluşturucuda `get_Box()` , döndürülen değer bir bir bir "(süresi  dolacak) değeridir. Herhangi bir değişkene atanmamış ve bu nedenle kapsam dışına geçmek üzere. Bu örneğe ilişkin mosyon sağlamak için, içeriği temsil eden büyük bir dize vektörü sunalım. Vektör ve dizelerini kopyalamak yerine, vector öğesinin artık yeni nesneye ait olması için "kutu" süresi dolan değerden "buar" ' A yapılan çağrı, `std::move` ve sınıflarının her ikisi de `vector` `string` kendi taşıma oluşturucularını uygulayacağından gereklidir.

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

Bir sınıf bir taşıma Oluşturucusu tanımlamıyorsa, Kullanıcı tarafından belirtilen kopya Oluşturucu, kopya atama işleci, taşıma atama işleci veya yıkıcısı yoksa derleyici örtük bir tane oluşturur. Açık veya örtük bir taşıma Oluşturucusu tanımlanmazsa, başka şekilde bir taşıma Oluşturucusu kullanan işlemler kopyalama oluşturucusunu kullanır. Bir sınıf bir taşıma Oluşturucusu veya taşıma ataması operatörü bildiriyorsa, örtük olarak belirtilen kopya Oluşturucu silindi olarak tanımlanır.

Örtük olarak tanımlanmış bir taşıma Oluşturucusu, sınıf türü olmayan bir üye yok edici veya derleyici, taşıma işlemi için hangi oluşturucuyu kullanacağınızı belirleyemediği sürece silinir.

Önemsiz olmayan bir taşıma oluşturucusunun nasıl yazılacağı hakkında daha fazla bilgi için bkz. [Taşıma Oluşturucuları ve taşıma atama işleçleri (C++)](../cpp/move-constructors-and-move-assignment-operators-cpp.md).

## <a name="explicitly-defaulted-and-deleted-constructors"></a><a name="explicitly_defaulted_and_deleted_constructors"></a> Açık olarak varsayılan ve silinen oluşturucular

Açıkça *varsayılan* kopya oluşturucuları, varsayılan oluşturucular, taşıma oluşturucuları, kopya atama işleçleri, taşıma atama işleçleri ve yok ediciler oluşturabilirsiniz. Tüm özel üye işlevlerini açık bir şekilde *silebilirsiniz* .

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

Daha fazla bilgi için bkz. [açıkça ayarlanmış ve silinen işlevler](../cpp/explicitly-defaulted-and-deleted-functions.md).

## <a name="constexpr-constructors"></a><a name="constexpr_constructors"></a> constexpr oluşturucuları

Bir [Oluşturucu,](constexpr-cpp.md)

- Bu, varsayılan olarak bildirilmiştir ya da genel olarak [constexpr işlevlerine](constexpr-cpp.md#constexpr_functions) yönelik tüm koşulları karşılar;
- sınıfın sanal temel sınıfı yok;
- parametrelerin her biri [sabit bir türdür](trivial-standard-layout-and-pod-types.md#literal_types);
- gövde bir işlev try-Block değil;
- Tüm statik olmayan veri üyeleri ve temel sınıf alt nesneleri başlatılır;
- Sınıf (a) değişken üyesi olan bir Union veya (b) anonim birleşimler içeriyorsa, birleşim üyelerinden yalnızca biri başlatılır;
- sınıf türündeki statik olmayan her veri üyesine ve tüm temel sınıf alt nesnelerinde bir constexpr Oluşturucusu vardır

## <a name="initializer-list-constructors"></a><a name="init_list_constructors"></a> Başlatıcı listesi oluşturucuları

Bir Oluşturucu, parametresi olarak [std:: initializer_list \<T\> ](../standard-library/initializer-list-class.md) alırsa ve diğer parametrelerin varsayılan bağımsız değişkenleri varsa, sınıf doğrudan başlatma yoluyla örneği oluşturulduğunda, bu Oluşturucu aşırı yükleme çözümlemesi ' nde seçilir. İnitializer_list, kabul edebilecek herhangi bir üyeyi başlatmak için kullanabilirsiniz. Örneğin, Box sınıfının (daha önce gösterilen) bir üyeye sahip olduğunu `std::vector<string>` varsayalım `m_contents` . Aşağıdaki gibi bir Oluşturucu sağlayabilirsiniz:

```cpp
    Box(initializer_list<string> list, int w = 0, int h = 0, int l = 0)
        : m_contents(list), m_width(w), m_height(h), m_length(l)
{}
```

Ardından aşağıdaki gibi Box nesneleri oluşturun:

```cpp
    Box b{ "apples", "oranges", "pears" }; // or ...
    Box b2(initializer_list<string> { "bread", "cheese", "wine" }, 2, 4, 6);
```

## <a name="explicit-constructors"></a><a name="explicit_constructors"></a> Açık oluşturucular

Bir sınıfta tek parametreli bir Oluşturucu varsa veya biri hariç tüm parametrelerin varsayılan bir değeri varsa parametre türü örtük olarak sınıf türüne dönüştürülebilir. Örneğin, `Box` sınıfının şunun gibi bir Oluşturucusu varsa:

```cpp
Box(int size): m_width(size), m_length(size), m_height(size){}
```

Şöyle bir kutu başlatmak mümkündür:

```cpp
Box b = 42;
```

Veya bir kutu alan işleve bir int geçirin:

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

Bu tür dönüştürmeler bazı durumlarda yararlı olabilir, ancak kodunuzda daha hafif ancak önemli hatalara neden olabilir. Genel bir kural olarak, **`explicit`** Bu tür bir örtük tür dönüştürmeyi engellemek için bir Oluşturucu (ve Kullanıcı tanımlı işleçler) anahtar sözcüğünü kullanmanız gerekir:

```cpp
explicit Box(int size): m_width(size), m_length(size), m_height(size){}
```

Oluşturucu açık olduğunda, bu satır bir derleyici hatasına neden olur: `ShippingOrder so(42, 10.8);` .  Daha fazla bilgi için bkz. [Kullanıcı tanımlı tür dönüştürmeleri](../cpp/user-defined-type-conversions-cpp.md).

## <a name="order-of-construction"></a><a name="order_of_construction"></a> Oluşturma sırası

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

Çıktı aşağıda verilmiştir:

```Output
Contained1 ctor
Contained2 ctor
BaseContainer ctor
Contained3 ctor
DerivedContainer ctor
```

Bir türetilmiş sınıf oluşturucusu her zaman bir taban sınıf oluşturucusunu çağırır, böylece bu sınıf ek bir çalışma yapılmadan önce tümüyle oluşturulmuş taban sınıflarına dayanabilir. Temel sınıf oluşturucuları türetme sırasına göre çağrılır — Örneğin, öğesinden türetildiyse, `ClassA` `ClassB` `ClassC` `ClassC` Oluşturucu önce, sonra `ClassB` Oluşturucu, ardından `ClassA` Oluşturucu olur.

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

## <a name="derived-constructors-and-extended-aggregate-initialization"></a><a name="extended_aggregate"></a> Türetilmiş oluşturucular ve genişletilmiş toplu başlatma

Bir temel sınıfın Oluşturucusu genel olmayan, ancak türetilmiş bir sınıf tarafından erişilebilir değilse, **/std: c++ 17** modu altında Visual Studio 2017 ve sonraki sürümlerde, türetilmiş türdeki bir nesneyi başlatmak için boş küme ayraçları kullanamazsınız.

Aşağıdaki örnek C++ 14 uyumlu davranışını gösterir:

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

C++ 17 ' de `Derived` artık bir toplam türü olarak kabul edilir. Bu, `Base` özel varsayılan oluşturucu aracılığıyla başlatmanın, genişletilmiş toplama başlatma kuralının bir parçası olarak doğrudan gerçekleşir anlamına gelir. Daha önce, `Base` özel Oluşturucu Oluşturucu aracılığıyla çağrılıydı `Derived` ve arkadaş bildirimi nedeniyle başarılı oldu.

Aşağıdaki örnekte, **/std: c++ 17** modunda Visual Studio 2017 ve sonraki sürümlerde c++ 17 davranışı gösterilmektedir:

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

### <a name="constructors-for-classes-that-have-multiple-inheritance"></a>Birden çok devralma sınıfına sahip sınıflar için oluşturucular

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

## <a name="delegating-constructors"></a><a name="delegating_constructors"></a> Temsilci oluşturucuları

Bir *temsilci Oluşturucu* , başlatma işinin bir kısmını yapmak için aynı sınıfta farklı bir oluşturucu çağırır. Bu, hepsi de benzer bir iş gerçekleştirmek zorunda olan birden çok Oluşturucu varsa yararlıdır. Ana mantığı bir oluşturucuda yazabilir ve diğerlerinden çağırabilirsiniz. Aşağıdaki önemsiz örnekte, Box (int), çalışma kutusunu (int, int, int) temsil eder:

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

Herhangi bir oluşturucunun işi biter bitmez, oluşturucular tarafından oluşturulan nesne tamamen başlatılır. Daha fazla bilgi için bkz. [oluşturucular Için temsilci seçme](../cpp/delegating-constructors.md).

## <a name="inheriting-constructors-c11"></a><a name="inheriting_constructors"></a> Devralan oluşturucular (C++ 11)

Türetilmiş bir sınıf, **`using`** Aşağıdaki örnekte gösterildiği gibi bir bildirimi kullanarak doğrudan temel sınıftan oluşturucular alabilir:

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

::: moniker range=">=msvc-150"

**Visual Studio 2017 ve üzeri**: **`using`** **/std: c++ 17** modundaki ifade, türetilmiş sınıftaki oluşturucularla aynı imzaya sahip olanlar hariç, temel sınıftan tüm oluşturucuların kapsamına getirir. Genel olarak, türetilen sınıf yeni veri üyeleri veya oluşturucular bildirmediği zaman devralma oluşturucularının kullanılması en iyisidir.

::: moniker-end

Bir sınıf şablonu, bu tür bir temel sınıf belirtiyorsa bir tür bağımsız değişkeninden tüm oluşturucuları devralınabilir:

```cpp
template< typename T >
class Derived : T {
    using T::T;   // declare the constructors from T
    // ...
};
```

Bu temel sınıfların aynı imzaya sahip oluşturucuları varsa, türetilen bir sınıf birden çok temel sınıftan türelemez.

## <a name="constructors-and-composite-classes"></a><a name="constructors_in_composite_classes"></a> Oluşturucular ve bileşik sınıflar

Sınıf türü üyeleri içeren sınıflar *bileşik sınıflar* olarak bilinir. Bileşik bir sınıfın sınıf türünde bir üyesi oluşturulduğunda, sınıfın kendisi çağrılmadan önce oluşturucu çağrılır. İçerilen bir sınıfın varsayılan bir oluşturucusu yoksa, bileşik sınıfın oluşturucusunda bir başlatma listesi kullanmalısınız. Önceki `StorageBox` örnekte, `m_label` üye değişkeninin türünü yeni bir `Label` sınıfa değiştirirseniz, hem temel sınıf oluşturucusunu hem de `m_label` değişkeni `StorageBox` oluşturucuda başlatmalısınız:

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

- [Kopya oluşturucuları ve kopya atama işleçleri](copy-constructors-and-copy-assignment-operators-cpp.md)
- [Taşıma oluşturucuları ve taşıma atama işleçleri](move-constructors-and-move-assignment-operators-cpp.md)
- [Temsilci oluşturucuları](delegating-constructors.md)

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve yapılar](classes-and-structs-cpp.md)
