---
title: union
description: Standart C++ union class türü ve anahtar sözcüğünün açıklaması, kullanımı ve kısıtlamaları.
ms.date: 08/18/2020
f1_keywords:
- union_cpp
helpviewer_keywords:
- class type [C++], union as
- union keyword [C++]
ms.assetid: 25c4e219-fcbb-4b7b-9b64-83f3252a92ca
no-loc:
- union
- struct
- enum
- class
- static
ms.openlocfilehash: a4dc07df5e7858dffe62478509ee1d8dc759ce96
ms.sourcegitcommit: f1752bf90b4f869633a859ace85439ca19e208b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/21/2020
ms.locfileid: "88722186"
---
# `union`

> [!NOTE]
> C++ 17 ve üzeri sürümlerde, `std::variant` class için tür açısından güvenli bir alternatiftir union .

, **`union`** Tüm üyelerin aynı bellek konumunu paylaştığı Kullanıcı tanımlı bir türdür. Bu tanım, belirli bir zamanda, union üyeleri listesinden birden fazla nesne içerebileceği anlamına gelir. Ayrıca, bir kaç üyenin ne olduğuna bakılmaksızın union , her zaman en büyük üyeyi depolamak için yeterli bellek kullandığını da gösterir.

, union Çok sayıda nesneniz ve sınırlı belleğiniz olduğunda belleğin tasarrufu için yararlı olabilir. Bununla birlikte, bir, union doğru şekilde kullanılması için ek bir değer gerektirir. Atadığınız aynı üyeye her zaman erişebildiğinizden emin olmanız sizin sorumluluğunuzdadır. Herhangi bir üye türü, önemsiz olmayan bir con struct veya varsa, bu üyeyi açıkça con ve yok etmek için ek kod yazmalısınız struct . Bir kullanmadan önce union , çözmeye çalıştığınız sorunun temel class ve türetilmiş türler kullanılarak daha iyi ifade edilip edilmeyeceğini göz önünde bulundurun class .

## <a name="syntax"></a>Syntax

> **`union`***`tag`* <sub>opt</sub> **`{`** opt *`member-list`***`};`**

### <a name="parameters"></a>Parametreler

*`tag`*<br/>
Öğesine verilen tür adı union .

*`member-list`*<br/>
unionİçerebilen Üyeler.

## <a name="declare-a-no-locunion"></a>Şunu bildirin union

unionAnahtar sözcüğünü kullanarak a bildirimini başlatın **`union`** ve üye listesini küme ayraçları içine alın:

```cpp
// declaring_a_union.cpp
union RecordType    // Declare a simple union type
{
    char   ch;
    int    i;
    long   l;
    float  f;
    double d;
    int *int_ptr;
};

int main()
{
    RecordType t;
    t.i = 5; // t holds an int
    t.f = 7.25; // t now holds a float
}
```

## <a name="use-a-no-locunion"></a>Şunu kullanın union

Önceki örnekte, union hangi üyenin verileri bulundurduğunu bilmeleri için ihtiyaçlarına erişen tüm kodlar. Bu sorunun en yaygın çözümü *ayrılmış union *olarak adlandırılır. union' A öğesine barındırır struct ve ' enum de şu anda depolanan üye türünü gösteren bir üye içerir union . Aşağıdaki örnekte temel desenler gösterilmektedir:

```cpp
#include <queue>

using namespace std;

enum class WeatherDataType
{
    Temperature, Wind
};

struct TempData
{
    int StationId;
    time_t time;
    double current;
    double max;
    double min;
};

struct WindData
{
    int StationId;
    time_t time;
    int speed;
    short direction;
};

struct Input
{
    WeatherDataType type;
    union
    {
        TempData temp;
        WindData wind;
    };
};

// Functions that are specific to data types
void Process_Temp(TempData t) {}
void Process_Wind(WindData w) {}

void Initialize(std::queue<Input>& inputs)
{
    Input first;
    first.type = WeatherDataType::Temperature;
    first.temp = { 101, 1418855664, 91.8, 108.5, 67.2 };
    inputs.push(first);

    Input second;
    second.type = WeatherDataType::Wind;
    second.wind = { 204, 1418859354, 14, 27 };
    inputs.push(second);
}

int main(int argc, char* argv[])
{
    // Container for all the data records
    queue<Input> inputs;
    Initialize(inputs);
    while (!inputs.empty())
    {
        Input const i = inputs.front();
        switch (i.type)
        {
        case WeatherDataType::Temperature:
            Process_Temp(i.temp);
            break;
        case WeatherDataType::Wind:
            Process_Wind(i.wind);
            break;
        default:
            break;
        }
        inputs.pop();

    }
    return 0;
}
```

Önceki örnekte, union içindeki içinde `Input` struct adı yoktur, bu nedenle *anonim* olarak adlandırılır union . Üyelerine üyelerine üye oldukları gibi doğrudan erişilebilir struct . Anonim kullanım hakkında daha fazla bilgi için union bkz. [anonim union ](#anonymous_unions) bölüm.

Önceki örnekte, class ortak bir tabandan türetilmiş türler kullanarak çözebileceğiniz bir sorun gösterilmektedir class . Kodunuzu, kapsayıcıdaki her nesnenin çalışma zamanı türüne göre Dallandırın. Kodunuzun bakımı ve anlaşılması daha kolay olabilir, ancak kullanmaktan de daha yavaş olabilir union . Ayrıca, ile union ilişkisiz türleri de saklayabilirsiniz. Bir, union değişkenin türünü değiştirmeden depolanan değerin türünü dinamik olarak değiştirmenize olanak sağlar union . Örneğin, `MyUnionType` öğeleri farklı türlerdeki farklı değerleri depolayan heterojen bir dizi oluşturabilirsiniz.

Örnekte ' nin kötüye kullanılması çok kolaydır `Input` struct . Verileri tutan üyeye erişmek için Ayrıştırıcıyı doğru bir şekilde kullanmak en iyisidir. Bir union **`private`** sonraki örnekte gösterildiği gibi özel erişim işlevleri sunarak ve sağlayarak kötüye kullanılmasına karşı koruma sağlayabilirsiniz.

## <a name="unrestricted-no-locunion-c11"></a>Kısıtlamasız union (c++ 11)

C++ 03 ve önceki sürümlerde, union static class türün hiçbir Kullanıcı tarafından sağlanmayan, struct struct tekörler veya atama işleçleri olmadığı sürece, bir türü olan veri olmayan üyeler içerebilir. C++ 11 ' de, bu kısıtlamalar kaldırılır. Bu tür bir üyeyi içine eklerseniz union , derleyici Kullanıcı tarafından sağlanmayan özel üye işlevlerini otomatik olarak işaretler **`deleted`** . , union Veya içinde anonim ise, union class struct ' ın veya Kullanıcı tarafından sağlanmayan tüm özel üye işlevleri class struct olarak işaretlenir **`deleted`** . Aşağıdaki örnek, bu durumun nasıl işleneceğini gösterir. Üyelerinden birinin union Bu özel işlemi gerektiren bir üyesi vardır:

```cpp
// for MyVariant
#include <crtdbg.h>
#include <new>
#include <utility>

// for sample objects and output
#include <string>
#include <vector>
#include <iostream>

using namespace std;

struct A
{
    A() = default;
    A(int i, const string& str) : num(i), name(str) {}

    int num;
    string name;
    //...
};

struct B
{
    B() = default;
    B(int i, const string& str) : num(i), name(str) {}

    int num;
    string name;
    vector<int> vec;
    // ...
};

enum class Kind { None, A, B, Integer };

#pragma warning (push)
#pragma warning(disable:4624)
class MyVariant
{
public:
    MyVariant()
        : kind_(Kind::None)
    {
    }

    MyVariant(Kind kind)
        : kind_(kind)
    {
        switch (kind_)
        {
        case Kind::None:
            break;
        case Kind::A:
            new (&a_) A();
            break;
        case Kind::B:
            new (&b_) B();
            break;
        case Kind::Integer:
            i_ = 0;
            break;
        default:
            _ASSERT(false);
            break;
        }
    }

    ~MyVariant()
    {
        switch (kind_)
        {
        case Kind::None:
            break;
        case Kind::A:
            a_.~A();
            break;
        case Kind::B:
            b_.~B();
            break;
        case Kind::Integer:
            break;
        default:
            _ASSERT(false);
            break;
        }
        kind_ = Kind::None;
    }

    MyVariant(const MyVariant& other)
        : kind_(other.kind_)
    {
        switch (kind_)
        {
        case Kind::None:
            break;
        case Kind::A:
            new (&a_) A(other.a_);
            break;
        case Kind::B:
            new (&b_) B(other.b_);
            break;
        case Kind::Integer:
            i_ = other.i_;
            break;
        default:
            _ASSERT(false);
            break;
        }
    }

    MyVariant(MyVariant&& other)
        : kind_(other.kind_)
    {
        switch (kind_)
        {
        case Kind::None:
            break;
        case Kind::A:
            new (&a_) A(move(other.a_));
            break;
        case Kind::B:
            new (&b_) B(move(other.b_));
            break;
        case Kind::Integer:
            i_ = other.i_;
            break;
        default:
            _ASSERT(false);
            break;
        }
        other.kind_ = Kind::None;
    }

    MyVariant& operator=(const MyVariant& other)
    {
        if (&other != this)
        {
            switch (other.kind_)
            {
            case Kind::None:
                this->~MyVariant();
                break;
            case Kind::A:
                *this = other.a_;
                break;
            case Kind::B:
                *this = other.b_;
                break;
            case Kind::Integer:
                *this = other.i_;
                break;
            default:
                _ASSERT(false);
                break;
            }
        }
        return *this;
    }

    MyVariant& operator=(MyVariant&& other)
    {
        _ASSERT(this != &other);
        switch (other.kind_)
        {
        case Kind::None:
            this->~MyVariant();
            break;
        case Kind::A:
            *this = move(other.a_);
            break;
        case Kind::B:
            *this = move(other.b_);
            break;
        case Kind::Integer:
            *this = other.i_;
            break;
        default:
            _ASSERT(false);
            break;
        }
        other.kind_ = Kind::None;
        return *this;
    }

    MyVariant(const A& a)
        : kind_(Kind::A), a_(a)
    {
    }

    MyVariant(A&& a)
        : kind_(Kind::A), a_(move(a))
    {
    }

    MyVariant& operator=(const A& a)
    {
        if (kind_ != Kind::A)
        {
            this->~MyVariant();
            new (this) MyVariant(a);
        }
        else
        {
            a_ = a;
        }
        return *this;
    }

    MyVariant& operator=(A&& a)
    {
        if (kind_ != Kind::A)
        {
            this->~MyVariant();
            new (this) MyVariant(move(a));
        }
        else
        {
            a_ = move(a);
        }
        return *this;
    }

    MyVariant(const B& b)
        : kind_(Kind::B), b_(b)
    {
    }

    MyVariant(B&& b)
        : kind_(Kind::B), b_(move(b))
    {
    }

    MyVariant& operator=(const B& b)
    {
        if (kind_ != Kind::B)
        {
            this->~MyVariant();
            new (this) MyVariant(b);
        }
        else
        {
            b_ = b;
        }
        return *this;
    }

    MyVariant& operator=(B&& b)
    {
        if (kind_ != Kind::B)
        {
            this->~MyVariant();
            new (this) MyVariant(move(b));
        }
        else
        {
            b_ = move(b);
        }
        return *this;
    }

    MyVariant(int i)
        : kind_(Kind::Integer), i_(i)
    {
    }

    MyVariant& operator=(int i)
    {
        if (kind_ != Kind::Integer)
        {
            this->~MyVariant();
            new (this) MyVariant(i);
        }
        else
        {
            i_ = i;
        }
        return *this;
    }

    Kind GetKind() const
    {
        return kind_;
    }

    A& GetA()
    {
        _ASSERT(kind_ == Kind::A);
        return a_;
    }

    const A& GetA() const
    {
        _ASSERT(kind_ == Kind::A);
        return a_;
    }

    B& GetB()
    {
        _ASSERT(kind_ == Kind::B);
        return b_;
    }

    const B& GetB() const
    {
        _ASSERT(kind_ == Kind::B);
        return b_;
    }

    int& GetInteger()
    {
        _ASSERT(kind_ == Kind::Integer);
        return i_;
    }

    const int& GetInteger() const
    {
        _ASSERT(kind_ == Kind::Integer);
        return i_;
    }

private:
    Kind kind_;
    union
    {
        A a_;
        B b_;
        int i_;
    };
};
#pragma warning (pop)

int main()
{
    A a(1, "Hello from A");
    B b(2, "Hello from B");

    MyVariant mv_1 = a;

    cout << "mv_1 = a: " << mv_1.GetA().name << endl;
    mv_1 = b;
    cout << "mv_1 = b: " << mv_1.GetB().name << endl;
    mv_1 = A(3, "hello again from A");
    cout << R"aaa(mv_1 = A(3, "hello again from A"): )aaa" << mv_1.GetA().name << endl;
    mv_1 = 42;
    cout << "mv_1 = 42: " << mv_1.GetInteger() << endl;

    b.vec = { 10,20,30,40,50 };

    mv_1 = move(b);
    cout << "After move, mv_1 = b: vec.size = " << mv_1.GetB().vec.size() << endl;

    cout << endl << "Press a letter" << endl;
    char c;
    cin >> c;
}
```

Bir union başvuruyu depolayamıyorum. , union Devralmayı da desteklemez. Bu, bir union taban olarak kullanamıyoruz class veya başka birinden class veya sanal işlevlere sahip olamaz.

## <a name="initialize-a-no-locunion"></a>Başlat union

unionKüme ayraçları içine alınmış bir ifade atayarak aynı deyimde bir bildirir ve başlatabilirsiniz. İfade değerlendirilir ve öğesinin ilk alanına atanır union .

```cpp
#include <iostream>
using namespace std;

union NumericType
{
    short       iValue;
    long        lValue;
    double      dValue;
};

int main()
{
    union NumericType Values = { 10 };   // iValue = 10
    cout << Values.iValue << endl;
    Values.dValue = 3.1416;
    cout << Values.dValue << endl;
}
/* Output:
10
3.141600
*/
```

, `NumericType` union Aşağıdaki şekilde gösterildiği gibi bellekte düzenlenir (kavramsal).

![Verilerin sayısal bir türde depolanması::: No-Loc (UNION):::](../cpp/media/vc38ul1.png "Bir NumericType::: No-Loc (UNION) içinde veri depolama:::") <br/>
Veri `NumericType` depolama alanı union

## <a name="anonymous-no-locunion"></a><a name="anonymous_unions"></a> Deðeri union

Anonim union , veya olmadan tanımlanmış bir *`class-name`* *`declarator-list`* .

> **`union  {`**  *`member-list`*  **`}`**

Anonim olarak belirtilen adlar union , üye olmayan değişkenler gibi doğrudan kullanılır. Anonim olarak belirtilen adların, union çevresindeki kapsamda benzersiz olması gerektiğini belirtir.

Anonim union , bu ek kısıtlamalara tabidir:

- Dosya veya ad alanı kapsamında bildirilirse, aynı zamanda olarak bildirilmelidir **`static`** .

- Yalnızca üyelere sahip olabilir **`public`** ; **`private`** **`protected`** anonim olarak bulunan ve üyeleri bir union hata oluşturur.

- Üye işlevleri olamaz.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve Yapılar](../cpp/classes-and-structs-cpp.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[`class`](../cpp/class-cpp.md)<br/>
[`struct`](../cpp/struct-cpp.md)
