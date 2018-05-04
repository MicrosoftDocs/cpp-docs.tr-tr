---
title: Birleşimler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- union_cpp
dev_langs:
- C++
helpviewer_keywords:
- class types [C++], unions as
- union keyword [C++]
ms.assetid: 25c4e219-fcbb-4b7b-9b64-83f3252a92ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 066f7c50940e6c68bb0fca554bb3bc56fc20b93c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="unions"></a>Birleşimler
A `union` tüm üyeleri aynı bellek konumuna paylaşmak bir kullanıcı tanımlı tür. Başka bir deyişle, belirli bir zamanda birden fazla nesne üyeleri listesinden UNION içerebilir. Ayrıca, UNION sahip kaç üye olsun, her zaman yalnızca yeterli bellek büyük üye depolamak için kullandığını anlamına gelir.  
  
 Birleşimler, nesneleri ve/veya sınırlı bellek çok sayıda olduğunda bellek tasarrufu için faydalı olabilir. Ancak her zaman için yazılmıştır son üyesini erişim sağlamak için sorumlu olduğu için doğru bir şekilde kullanmak için ek bakım gerektirir. Tüm üye türleri Önemsiz olmayan bir oluşturucu varsa, açıkça oluşturmak ve bu üyede yok etmek için ek kod yazmanız gerekir. Çözmeye çalıştığınız sorunu daha iyi bir temel sınıfı kullanılarak ifade edilebilir ve türetilmiş sınıfları UNION kullanmadan önce göz önünde bulundurun.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
union [name]  { member-list };  
```  
  
#### <a name="parameters"></a>Parametreler  
 `name`  
 Birleşime verilen tür adı.  
  
 `member-list`  
 UNION içerebilir üyeleri. Açıklamalar bakın.  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="declaring-a-union"></a>Bir Birleşimi Bildirme  
 Bir birleşim bildirimi başlamak `union` anahtar sözcüğü ve kaşlı ayraç üye listesini alın:  
  
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
    t.f = 7.25 // t now holds a float   
}  
```  
  
## <a name="using-unions"></a>Birleşimler kullanma  
 Önceki örnekte, UNION erişen herhangi bir kod hangi üye verileri tutan bilmesi gerekir. En yaygın bu sorunun birleşim içinde şu anda depolanmakta veri türünü belirten bir ek numaralandırma üyesi birlikte bir yapı içinde UNION kapsamak için çözümüdür. Bu adlı bir *UNION ayrılmış* ve aşağıdaki örnek, temel düzeni gösterir.  
  
```cpp  
#include "stdafx.h"  
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
  
 Önceki örnekte, birleşim giriş yapı içinde hiçbir adı olduğuna dikkat edin. Bu anonim bir birleşim ve yapının doğrudan üyesi değilmiş gibi üyeleri erişilebilir. Anonim birleşimler hakkında daha fazla bilgi için aşağıdaki bölümüne bakın.  
  
 Elbette, önceki örnekte de ortak bir taban sınıftan türetilen sınıflarını kullanarak ve kapsayıcıdaki her nesnenin çalışma zamanı türüne göre kodunuzu dallanma çözülmesi bir sorunu gösterir. Bu kod korumak ve, ama anlamak daha kolay ayrıca birleşimler kullanmaktan daha yavaş olabileceğini neden olabilir. Ayrıca, bir birleşimi ile tamamen ilişkisiz türleri depolamak ve dinamik olarak birleşim değişken türünü değiştirmeden depolanan değerin türünü değiştirin. Bu nedenle, farklı türlerde farklı değerler öğeleri depolamak MyUnionType heterojen bir dizi oluşturabilirsiniz.  
  
 Unutmayın `Input` önceki örnekte yapısı kolaylıkla kötüye olabilir. Tamamen Ayrıştırıcıyı doğru verilerini tutan üye erişmek için kullanılacak kullanıcı kadar da değil. UNION özel yaparak kötüye karşı koruyabilir ve özel erişim sağlayan, sonraki örnekte gösterildiği şekilde çalışır.  
  
## <a name="unrestricted-unions-c11"></a>Kısıtlanmamış birleşimler (C ++ 11)  
 Hiçbir kullanıcı tarafından sağlanan Oluşturucular, Yıkıcılar veya atama işleçleri türüne sahip olduğu sürece C ++ 03 ve daha önceki bir birleşim sınıfı türüyle statik olmayan veri üyeleri içerebilir. C ++ 11'de, bu sınırlamalar kaldırılmıştır. Böyle bir üyesi birleşim içinde eklerseniz derleyici otomatik olarak kullanıcı tarafından silindi olarak sağlanan olmayan herhangi bir özel üye işlevleri işaretleyin. UNION anonim bir birleşim sınıfta veya yapı içinde ise, kullanıcı tarafından sağlanan olmayan özel üye işlevleri sınıf veya yapı silinmiş olarak işaretlenmiş. Aşağıdaki örnek, bir birleşim üyeleri bu özel işleme gerektiren bir üyeye sahip olduğu durumda nasıl ele alınacağını gösterir:  
  
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
  
 Birleşimler başvuruları depolanamıyor. Birleşimler devralma desteklemiyorsa, bu nedenle bir birleşim bir temel sınıf olarak kullanılan veya başka bir sınıftan veya sanal işlevlere sahiptir.  
  
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
  
 ![Bir sayısal tür birleşim veri depolama](../cpp/media/vc38ul1.png "vc38UL1")  
Verilerin NumericType Birleşiminde Depolanması  
  
## <a name="anonymous_unions"></a> Anonim birleşimler  
 Anonim birleşimler olmadan bildirilen birleşimler olan bir *sınıf adı* veya *bildirimcisi listesi*.  
  
```cpp  
union  {  member-list  }    
```  
  
Anonim bir birleşimde bildirilen adlar, üye olmayan değişkenlerde olduğu gibi doğrudan kullanılır. Bu nedenle, çevreleyen kapsamdaki anonim bir birleşim içinde bildirilen adları benzersiz olmalıdır.  
  
Adlandırılmış birleşimler kısıtlamalarına ek olarak, bu ek sınırlamalara tabidir anonim birleşimler şunlardır:  
  
-   Olarak da bildirilmelidir **statik** dosya veya ad alanı kapsamda bildirilen durumunda.  
  
-   Yalnızca genel üyeleri olabilir; anonim birleşimlerdeki özel ve korumalı üyeler hata oluşturur.  
  
-   Bunlar, üye işlevleri sahip olamaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar ve yapılar](../cpp/classes-and-structs-cpp.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [sınıfı](../cpp/class-cpp.md)   
 [struct](../cpp/struct-cpp.md)