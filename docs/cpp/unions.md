---
title: Birleşimler
ms.date: 05/06/2019
f1_keywords:
- union_cpp
helpviewer_keywords:
- class types [C++], unions as
- union keyword [C++]
ms.assetid: 25c4e219-fcbb-4b7b-9b64-83f3252a92ca
ms.openlocfilehash: 8a4ea3ae325eb5882c2f8b2524bbc156d12ffcc6
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79418372"
---
# <a name="unions"></a>Birleşimler

> [!NOTE]
> C++ 17 ve üzeri sürümlerde **std:: Variant** sınıfı birleşimler için tür açısından güvenli bir alternatiftir.

**Birleşim** , tüm üyelerin aynı bellek konumunu paylaştığı Kullanıcı tanımlı bir türdür. Bu, bir birleşimin üye listesinden birden fazla nesne içerebileceği anlamına gelir. Ayrıca, bir birleşimin kaç üye olduğuna bakılmaksızın, her zaman en büyük üyeyi depolamak için yeterli bellek kullandığından da bu da anlamına gelir.

Birleşimler, çok sayıda nesneniz ve/veya sınırlı belleğiniz olduğunda belleğin tasarrufu için yararlı olabilir. Ancak, her zaman yazılan son üyeye erişiminizin sağlanmasından sorumlu olduğunuzdan, doğru şekilde kullanılması için daha fazla dikkatli gereksinim duyar. Herhangi bir üye türünün önemsiz olmayan bir Oluşturucusu varsa, bu üyeyi açıkça oluşturmak ve yok etmek için ek kod yazmalısınız. Bir UNION kullanmadan önce, çözmeye çalıştığınız sorunun temel sınıf ve türetilmiş sınıflar kullanılarak daha iyi ifade edilip edilmeyeceğini göz önünde bulundurun.

## <a name="syntax"></a>Sözdizimi

```cpp
union [name]  { member-list };
```

### <a name="parameters"></a>Parametreler

*ada*<br/>
Birleşime verilen tür adı.

*üye listesi*<br/>
Birleşimin içerebileceği Üyeler. Bkz. açıklamalar.

## <a name="remarks"></a>Açıklamalar

## <a name="declaring-a-union"></a>Bir Birleşimi Bildirme

**UNION anahtar sözcüğüyle** birleşim bildirimini başlatın ve üye listesini küme ayraçları içine alın:

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

## <a name="using-unions"></a>Birleşimler kullanma

Önceki örnekte, birleşimle erişen tüm kodlar, verileri tutan üyenin öğrenilmesi gerekir. Bu sorunun en yaygın çözümü, UNION 'yi, birleşimde Şu anda depolanmakta olan verilerin türünü belirten ek bir numaralandırma üyesiyle birlikte bir yapıda çevrelemektir. Buna *ayrılmış birleşim* denir ve aşağıdaki örnekte temel desenler gösterilmektedir.

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

// Container for all the data records
queue<Input> inputs;
void Initialize();

int main(int argc, char* argv[])
{
    Initialize();
    while (!inputs.empty())
    {
        Input i = inputs.front();
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

void Initialize()
{
    Input first, second;
    first.type = WeatherDataType::Temperature;
    first.temp = { 101, 1418855664, 91.8, 108.5, 67.2 };
    inputs.push(first);

    second.type = WeatherDataType::Wind;
    second.wind = { 204,1418859354, 14, 27 };
    inputs.push(second);
}
```

Önceki örnekte, Input struct içindeki birleşimin bir adı olmadığını unutmayın. Bu anonim bir birleşimdir ve kendi üyelerine, yapısına doğrudan üye gibi erişilebilir. Anonim birleşimler hakkında daha fazla bilgi için aşağıdaki bölüme bakın.

Tabii ki, önceki örnekte, ortak bir taban sınıftan türetilen sınıflar kullanılarak çözülebilmesine ve kodu kapsayıcıdaki her bir nesnenin çalışma zamanı türüne göre Dallandırmanın bir sorunu gösterilmektedir. Bu, bakımı ve anlaşılması daha kolay olan bir koda neden olabilir, ancak birleşimler kullanmaktan daha da yavaş olabilir. Ayrıca, bir birleşimle tamamen ilişkisiz türler saklayabilir ve birleşim değişkeninin türünü değiştirmeden depolanan değerin türünü dinamik olarak değiştirebilirsiniz. Bu nedenle, öğeleri farklı türlerdeki farklı değerleri depolayan MyUnionType öğesinin heterojen bir dizisini oluşturabilirsiniz.

Yukarıdaki örnekte `Input` yapısının kolayca kötüye kullanılabilir olabileceğini unutmayın. Verileri tutan üyeye erişmek için Ayrıştırıcıyı doğru bir şekilde kullanmak tamamen kullanıcıya tamamıyla yapılır. UNION Private yaparak ve sonraki örnekte gösterildiği gibi özel erişim işlevleri sunarak kötüye kullanılmasına karşı koruma sağlayabilirsiniz.

## <a name="unrestricted-unions-c11"></a>Kısıtlanmamış birleşimler (C++ 11)

C++ 03 ' de ve önceki sürümlerde, türün Kullanıcı tarafından sunulan oluşturucular, Yıkıcılar veya atama işleçleri olmadığı sürece sınıf türünde statik olmayan veri üyeleri bulunabilir. C++ 11 ' de, bu kısıtlamalar kaldırılır. Bu tür bir üyeyi birleşiminize eklerseniz, derleyici Kullanıcı tarafından, silinen olarak sağlanmayan özel üye işlevleri otomatik olarak işaretleyecek. Birleşim, bir sınıf veya yapı içindeki anonim bir birleşimse, sınıfın veya yapının içinde kullanıcı olmayan özel üye işlevleri silindi olarak işaretlenir. Aşağıdaki örnek, birleşimin üyelerinden birinin bu özel işlemi gerektiren bir üyeye sahip olduğu durumu nasıl işleyeceğinizi göstermektedir:

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
#include <queue>
#include <iostream>
using namespace std;

enum class WeatherDataType
{
    Temperature, Wind
};

struct TempData
{
    TempData() : StationId(""), time(0), current(0), maxTemp(0), minTemp(0) {}
    TempData(string id, time_t t, double cur, double max, double min)
        : StationId(id), time(t), current(cur), maxTemp(max), minTemp(0) {}
    string StationId;
    time_t time = 0;
    double current;
    double maxTemp;
    double minTemp;
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
    Input() {}
    Input(const Input&) {}

    ~Input()
    {
        if (type == WeatherDataType::Temperature)
        {
            temp.StationId.~string();
        }
    }

    WeatherDataType type;
    void SetTemp(const TempData& td)
    {
        type = WeatherDataType::Temperature;

        // must use placement new because of string member!
        new(&temp) TempData(td);
    }

    TempData GetTemp()
    {
        if (type == WeatherDataType::Temperature)
            return temp;
        else
            throw logic_error("Can't return TempData when Input holds a WindData");
    }
    void SetWind(WindData wd)
    {
        // Explicitly delete struct member that has a
        // non-trivial constructor
        if (type == WeatherDataType::Temperature)
        {
            temp.StationId.~string();
        }
        wind = wd; //placement new not required.
    }
    WindData GetWind()
    {
        if (type == WeatherDataType::Wind)
        {
            return wind;
        }
        else
            throw logic_error("Can't return WindData when Input holds a TempData");
    }

private:

    union
    {
        TempData temp;
        WindData wind;
    };
};
```

Birleşimler başvuruları depoalamaz. Birleşimler devralmayı desteklemez, bu nedenle bir birleşim temel sınıf olarak kullanılamaz, ya da başka bir sınıftan devralınamaz veya sanal işlevlere sahip olamaz.

## <a name="initializing-unions"></a>Birleşimler başlatılıyor

Küme ayraçları içine alınmış bir ifade atayarak aynı deyimde bir birleşimi bildirebilir ve başlatabilirsiniz. İfade değerlendirilir ve birleşimin ilk alanına atanır.

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
    cout << Values.dValue) << endl;
}
/* Output:
10
3.141600
*/
```

`NumericType` birleşimi, bellekte (kavramsal olarak) aşağıdaki şekilde gösterildiği gibi düzenlenir.

![Sayısal tür birleşimde veri depolama](../cpp/media/vc38ul1.png "NumericType birleşimi içinde veri depolama") <br/>
Verilerin NumericType Birleşiminde Depolanması

## <a name="anonymous_unions"></a>Anonim birleşimler

Anonim birleşimler, bir *sınıf adı* veya *bildirimci listesi*olmadan belirtilen birleşimlerdir.

```cpp
union  {  member-list  }
```

Anonim bir birleşimde bildirilen adlar, üye olmayan değişkenlerde olduğu gibi doğrudan kullanılır. Bu nedenle, anonim bir birleşimde belirtilen adların, çevresindeki kapsamda benzersiz olması gerekir.

Adlandırılmış birleşimler için kısıtlamalara ek olarak, anonim birleşimler bu ek kısıtlamalara tabidir:

- Ayrıca, dosya veya ad alanı kapsamında bildirilirse, **statik** olarak bildirilmelidir.

- Yalnızca **ortak** üyelere sahip olabilirler; anonim Birleşimlerdeki **özel** ve **korunan** Üyeler hata oluşturur.

- Üye işlevleri olamaz.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve Yapılar](../cpp/classes-and-structs-cpp.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[class](../cpp/class-cpp.md)<br/>
[struct](../cpp/struct-cpp.md)