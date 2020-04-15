---
title: Ad Alanları (C++)
ms.date: 08/30/2017
f1_keywords:
- namespace_CPP
- using_CPP
helpviewer_keywords:
- namespaces [C++]
ms.assetid: d1a5a9ab-1cad-47e6-a82d-385bb77f4188
ms.openlocfilehash: 4957ec5a5face860d2e39861eddc8f7e5abe9370
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367909"
---
# <a name="namespaces-c"></a>Ad Alanları (C++)

Ad alanı, içindeki tanımlayıcılara (tür adları, işlevler, değişkenler vb.) kapsam sağlayan bir bildirim seli dir. Ad alanları, kodu mantıksal gruplar halinde düzenlemek ve özellikle kod tabanınız birden çok kitaplık içeriyorsa oluşabilecek ad çakışmalarını önlemek için kullanılır. Ad alanı kapsamındaki tüm tanımlayıcılar, nitelik sizde birbiriyle görülebilir. Ad alanı dışındaki tanımlayıcılar, her tanımlayıcı için tam nitelikli adı kullanarak üyelere erişebilir, `std::vector<std::string> vec;`örneğin, veya tek bir tanımlayıcı için [bir](../cpp/using-declaration.md) bildirim`using std::string`bildirimi (), veya ad alanındaki tüm tanımlayıcılar için`using namespace std;` [bir yönerge kullanarak](../cpp/namespaces-cpp.md#using_directives) ( ). Üstbilgi dosyalarındaki kod her zaman tam nitelikli ad alanı adını kullanmalıdır.

Aşağıdaki örnek, bir ad alanı bildirimi ni ve ad alanı dışındaki kodun üyelerine erişebileceği üç yolu gösterir.

```cpp
namespace ContosoData
{
    class ObjectManager
    {
    public:
        void DoSomething() {}
    };
    void Func(ObjectManager) {}
}
```

Tam nitelikli adı kullanın:

```cpp
ContosoData::ObjectManager mgr;
mgr.DoSomething();
ContosoData::Func(mgr);
```

Bir tanımlayıcıyı kapsamına getirmek için bir kullanım bildirimi kullanın:

```cpp
using ContosoData::ObjectManager;
ObjectManager mgr;
mgr.DoSomething();
```

Ad alanındaki her şeyi kapsamına getirmek için bir kullanım yönergesi kullanın:

```cpp
using namespace ContosoData;

ObjectManager mgr;
mgr.DoSomething();
Func(mgr);
```

## <a name="using-directives"></a><a id="using_directives"></a>direktifleri kullanarak

**Kullanma** yönergesi, ad **alanındaki** tüm adların açık bir niteleyici olarak ad *alanı adı* olmadan kullanılmasına izin verir. Bir ad alanında birkaç farklı tanımlayıcı kullanıyorsanız, uygulama dosyasında (örn. *.cpp) bir kullanım yönergesi kullanın; yalnızca bir veya iki tanımlayıcı kullanıyorsanız, yalnızca bu tanımlayıcıları kapsama getirmek için bir deklarasyon kullanmayı düşünün, ad alanındaki tüm tanımlayıcıları değil. Yerel bir değişken adı ad alanı değişkeniyle aynı ada sahipse, ad alanı değişkeni gizlenir. Genel bir değişken olarak aynı ada sahip ad alanı değişkeninin bulundurulması bir hatadır.

> [!NOTE]
> Bir kullanım yönergesi .cpp dosyasının en üstüne (dosya kapsamında) veya bir sınıf veya işlev tanımının içine yerleştirilebilir.
>
> Genel olarak, üstbilgi dosyalarına yönergeleri kullanmaktan kaçının (*.h) çünkü bu üstbilgi içeren herhangi bir dosya ad alanındaki her şeyi kapsama getirir ve bu da hata ayıklama nın çok zor olan ad gizleme ve ad çakışması sorunlarına neden olabilir. Üstbilgi dosyasında her zaman tam nitelikli adlar kullanın. Bu adlar çok uzun sürerse, kısaltmak için bir ad alanı diğer adı kullanabilirsiniz. (Aşağıya bakın.)

## <a name="declaring-namespaces-and-namespace-members"></a>Ad boşluklarını ve ad alanı üyelerini bildirme

Genellikle, üstbilgi dosyasında bir ad alanı bildirirsiniz. İşlev uygulamalarınız ayrı bir dosyadaysa, bu örnekte olduğu gibi işlev adlarını hak layın.

```cpp
//contosoData.h
#pragma once
namespace ContosoDataServer
{
    void Foo();
    int Bar();
}
```

Contosodata.cpp'deki işlev uygulamaları, dosyanın en üstüne **bir kullanım** yönergesi yerleştirseniz bile tam nitelikli adı kullanmalıdır:

```cpp
#include "contosodata.h"
using namespace ContosoDataServer;

void ContosoDataServer::Foo() // use fully-qualified name here
{
   // no qualification needed for Bar()
   Bar();
}

int ContosoDataServer::Bar(){return 0;}
```

Ad alanı, tek bir dosyada ve birden çok dosyada birden çok blokta bildirilebilir. Derleyici, ön işleme sırasında parçaları birleştirir ve ortaya çıkan ad alanı tüm parçalarda bildirilen tüm üyeleri içerir. Bunun bir örneği, standart kitaplıktaki üstbilgi dosyalarının her birinde bildirilen std ad alanıdır.

Adlandırılmış ad alanının üyeleri, tanımlanan adın açık niteliği yle beyan edildikleri ad alanının dışında tanımlanabilir. Ancak, tanım, bildirimin ad alanını içeren bir ad alanında bildirim noktasından sonra görünmelidir. Örneğin:

```cpp
// defining_namespace_members.cpp
// C2039 expected
namespace V {
    void f();
}

void V::f() { }        // ok
void V::g() { }        // C2039, g() is not yet a member of V

namespace V {
    void g();
}
```

Ad alanı üyeleri birden çok üstbilgi dosyasında bildirildiğinde ve bu üstbilgi öğelerini doğru sıraya dahil etmediğinizde bu hata oluşabilir.

## <a name="the-global-namespace"></a>Genel ad alanı

Bir tanımlayıcı açık bir ad alanında bildirilmemişse, örtük genel ad alanının bir parçasıdır. Genel olarak, giriş noktası [ana Fonksiyonu](../c-language/main-function-and-program-execution.md)dışında, genel ad alanında olması gereken, mümkün olduğunda genel kapsamda bildirimler yapmaktan kaçınmaya çalışın. Genel bir tanımlayıcıyı açıkça nitelemek için, 'deki `::SomeFunction(x);`gibi adsız kapsam çözümleme işleci'ni kullanın. Bu, tanımlayıcıyı başka bir ad alanında aynı ada sahip herhangi bir şeyden ayırt edecek ve ayrıca kodunuzu başkalarının anlamasını kolaylaştırmaya yardımcı olur.

## <a name="the-std-namespace"></a>std ad alanı

Tüm C++ standart kitaplık türleri `std` ve işlevleri, içinde `std`iç içe geçen ad alanında veya ad alanlarında bildirilir.

## <a name="nested-namespaces"></a>İç içe ad alanları

Ad alanları iç içe olabilir. Normal iç içe geçen ad alanı, üst öğesinin üyelerine niteliksiz erişime sahiptir, ancak üst üyelerin aşağıdaki örnekte gösterildiği gibi iç içe geçen ad alanına (satır adı olarak bildirilmedikçe) niteliksiz erişimi yoktur:

```cpp
namespace ContosoDataServer
{
    void Foo();

    namespace Details
    {
        int CountImpl;
        void Ban() { return Foo(); }
    }

    int Bar(){...};
    int Baz(int i) { return Details::CountImpl; }
}
```

Normal iç içe ad alanları, üst ad alanının ortak arabiriminin parçası olmayan iç uygulama ayrıntılarını kapsüllemek için kullanılabilir.

## <a name="inline-namespaces-c-11"></a>Satır ara alanları (C++ 11)

Sıradan bir iç içe ad alanının aksine, satır içinde bir ad alanının üyeleri üst ad alanının üyeleri olarak kabul edilir. Bu özellik, aşırı yüklü işlevlerde bağımsız değişkenbağımlı aramanın, üst ve iç içe geçen satır ara boşlukta aşırı yüklenen işlevler üzerinde çalışmasını sağlar. Ayrıca, satır satır ad alanında bildirilen bir şablon için bir üst ad alanında uzmanlık beyan etmenizi sağlar. Aşağıdaki örnek, dış kodun varsayılan olarak satır içinde ad alanına nasıl bağdaştırdığını gösterir:

```cpp
//Header.h
#include <string>

namespace Test
{
    namespace old_ns
    {
        std::string Func() { return std::string("Hello from old"); }
    }

    inline namespace new_ns
    {
        std::string Func() { return std::string("Hello from new"); }
    }
}

#include "header.h"
#include <string>
#include <iostream>

int main()
{
    using namespace Test;
    using namespace std;

    string s = Func();
    std::cout << s << std::endl; // "Hello from new"
    return 0;
}
```

Aşağıdaki örnek, satır satır ad alanında bildirilen bir şablonun üst öğesinde nasıl uzmanlık bildirebileceğinizi gösterir:

```cpp
namespace Parent
{
    inline namespace new_ns
    {
         template <typename T>
         struct C
         {
             T member;
         };
    }
     template<>
     class C<int> {};
}
```

Kitaplığın ortak arabirimindeki değişiklikleri yönetmek için satır içinde ad alanlarını sürüm oluşturma mekanizması olarak kullanabilirsiniz. Örneğin, tek bir üst ad alanı oluşturabilir ve arabirimin her sürümünü üst öğenin içinde iç içe olan kendi ad alanında saklayabilirsiniz. En son veya tercih edilen sürümü tutan ad alanı satır altı olarak niteliklidir ve bu nedenle üst ad alanının doğrudan bir üyesi yatsın. Üst öğeyi çağıran istemci kodu::Sınıf otomatik olarak yeni koda bağlanır. Eski sürümü kullanmayı tercih eden istemciler, bu koda sahip iç içe giden ad alanına tam nitelikli yolu kullanarak bu sürüme erişmeye devam edebilir.

Satır araanahtar sözcüğü, bir derleme birimindeki ad alanının ilk bildirimine uygulanmalıdır.

Aşağıdaki örnekte, her biri iç içe geçen bir ad alanında olmak üzere bir arabirimin iki sürümü gösterilmektedir. `v_20` Ad alanı `v_10` arabirimden bazı değişiklikler vardır ve satır adı olarak işaretlenir. Yeni kitaplığı ve çağrıları `Contoso::Funcs::Add` kullanan istemci kodu v_20 sürümünü çağırır. Aramaya `Contoso::Funcs::Divide` çalışan kod artık bir derleme zaman hatası alır. Bu işleve gerçekten ihtiyaç duyarlarsa, `v_10` yine de `Contoso::v_10::Funcs::Divide`açıkça arayarak sürüme erişebilirler.

```cpp
namespace Contoso
{
    namespace v_10
    {
        template <typename T>
        class Funcs
        {
        public:
            Funcs(void);
            T Add(T a, T b);
            T Subtract(T a, T b);
            T Multiply(T a, T b);
            T Divide(T a, T b);
        };
    }

    inline namespace v_20
    {
        template <typename T>
        class Funcs
        {
        public:
            Funcs(void);
            T Add(T a, T b);
            T Subtract(T a, T b);
            T Multiply(T a, T b);
            std::vector<double> Log(double);
            T Accumulate(std::vector<T> nums);
      };
    }
}
```

## <a name="namespace-aliases"></a><a id="namespace_aliases"></a>Ad alanı takma adları

Ad alanı adlarının benzersiz olması gerekir, bu da genellikle çok kısa olmaması gerektiği anlamına gelir. Bir adın uzunluğu kodun okunmasını zorlaştırıyorsa veya yönergeleri kullanmanın kullanılamayacağı bir üstbilgi dosyasına yazmak can sıkıcıysa, gerçek adın kısaltması olarak hizmet veren bir ad alanı adı yapabilirsiniz. Örneğin:

```cpp
namespace a_very_long_namespace_name { class Foo {}; }
namespace AVLNN = a_very_long_namespace_name;
void Bar(AVLNN::Foo foo){ }
```

## <a name="anonymous-or-unnamed-namespaces"></a>anonim veya adsız ad boşlukları

Açık bir ad alanı oluşturabilir, ancak ona bir ad veremezsin:

```cpp
namespace
{
    int MyFunc(){}
}
```

Bu adsız veya anonim ad alanı olarak adlandırılır ve değişken bildirimlerini diğer dosyalardaki kodlara görünmez yapmak istediğinizde (örneğin, adlandırılmış bir ad alanı oluşturmak zorunda kalmadan iç bağlantı vermek) yararlıdır. Aynı dosyadaki tüm kodlar tanımlayıcıları adsız bir ad alanında görebilir, ancak tanımlayıcılar, ad alanının kendisiyle birlikte bu dosyanın dışında veya daha doğrusu çeviri biriminin dışında görünmez.

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimler ve Tanımlar](declarations-and-definitions-cpp.md)
