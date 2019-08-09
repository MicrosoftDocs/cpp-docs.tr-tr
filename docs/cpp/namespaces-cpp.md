---
title: Ad Alanları (C++)
ms.date: 08/30/2017
f1_keywords:
- namespace_CPP
- using_CPP
helpviewer_keywords:
- namespaces [C++]
ms.assetid: d1a5a9ab-1cad-47e6-a82d-385bb77f4188
ms.openlocfilehash: ae3006dd1b17ec38240a318af6cfcac5c7d6bf49
ms.sourcegitcommit: bd7ddc044f9083246614b602ef6a758775313214
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68866034"
---
# <a name="namespaces-c"></a>Ad Alanları (C++)

Ad alanı, tanımlayıcılara kapsam sağlayan bildirime dayalı bir bölgedir (türlerin, işlevlerin, değişkenlerin adları, vb.). Ad alanları, kodu mantıksal gruplar halinde düzenlemek ve özellikle kod tabanınız birden çok kitaplık içerdiğinde ortaya çıkabilecek ad çakışmalarını engellemek için kullanılır. Ad alanı kapsamındaki tüm tanımlayıcılar, nitelendirme olmadan bir diğeri ile görünür. Ad alanı dışındaki tanımlayıcılar, her tanımlayıcı için tam adı veya örneğin `std::vector<std::string> vec;`tek bir tanımlayıcı ( [](../cpp/using-declaration.md) `using std::string`) veya bir [using yönergesini](../cpp/namespaces-cpp.md#using_directives) kullanarak üyelere erişebilir. ad alanındaki tanımlayıcılar (`using namespace std;`). Üstbilgi dosyalarındaki kod her zaman tam nitelikli ad alanı adını kullanmalıdır.

Aşağıdaki örnek bir ad alanı bildirimi ve ad alanı dışındaki kodun üyelerine erişmesi için üç yol gösterir.

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

Bir tanımlayıcıyı kapsama getirmek için using bildirimi kullanın:

```cpp
using ContosoData::ObjectManager;
ObjectManager mgr;
mgr.DoSomething();
```

Ad alanındaki her şeyi kapsama getirmek için bir using yönergesi kullanın:

```cpp
using namespace ContosoData;

ObjectManager mgr;
mgr.DoSomething();
Func(mgr);
```

## <a id="using_directives"></a>using yönergeleri

**Using** yönergesi, bir **ad** alanındaki tüm adların açık bir niteleyici olarak *ad alanı adı* olmadan kullanılmasına izin verir. Bir ad alanında birkaç farklı tanımlayıcı kullanıyorsanız, uygulama dosyasında (ör. *. cpp) bir using yönergesi kullanın; yalnızca bir veya iki tanımlayıcı kullanıyorsanız, bu tanımlayıcıları yalnızca kapsama getirmek için bir using bildirimi düşünün ve ad alanındaki tanımlayıcıların tümünü değil. Yerel bir değişken adı ad alanı değişkeniyle aynı ada sahipse, ad alanı değişkeni gizlenir. Genel bir değişken olarak aynı ada sahip ad alanı değişkeninin bulundurulması bir hatadır.

> [!NOTE]
>  Bir using yönergesi, bir. cpp dosyasının (dosya kapsamında) veya bir sınıf ya da işlev tanımının içinde yer alabilir.
>
>  Genel olarak, bu üst bilgiyi içeren herhangi bir dosya ad alanındaki her şeyi kapsama alanına getirtiğinden ve hata ayıklamanın çok zor olduğu ad çakışmasına yol açabilecek şekilde, üst bilgi dosyalarında (*. h) yönergeleri kullanmaktan kaçının. Üst bilgi dosyasında her zaman tam nitelikli adlar kullanın. Bu adlar çok uzunsa, bunları kısaltmak için bir ad alanı diğer adı kullanabilirsiniz. (Aşağıya bakın.)

## <a name="declaring-namespaces-and-namespace-members"></a>Ad alanlarını ve ad alanı üyelerini bildirme

Genellikle, bir başlık dosyasında bir ad alanı bildirirsiniz. İşlev uygulamalarınız ayrı bir dosya içinde ise, bu örnekte olduğu gibi işlev adlarını niteleyin.

```cpp
//contosoData.h
#pragma once
namespace ContosoDataServer
{
    void Foo();
    int Bar();
}
```

Contosodata. cpp içindeki işlev uygulamaları, dosyanın en üstüne bir **using** yönergesi yerleştirseniz bile tam nitelikli adı kullanmalıdır:

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

Bir ad alanı, tek bir dosyada ve birden çok dosyada birden çok blok halinde bildirilebilecek. Derleyici, ön işleme sırasında parçaları birleştirir ve sonuçta elde edilen ad alanı tüm parçalar içinde belirtilen tüm üyeleri içerir. Standart Kitaplığı 'ndaki üst bilgi dosyalarında belirtilen std ad alanı buna bir örnektir.

Adlandırılmış bir ad alanının üyeleri, tanımlanmakta olan adın açık nitelikle bildirildiği ad alanı dışında tanımlanabilir. Ancak, tanım, bildirimin ad alanını içeren bir ad alanındaki bildirimin öğesinden sonra gelmelidir. Örneğin:

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

Bu hata, ad alanı üyeleri birden çok başlık dosyasında bildirildiği zaman oluşabilir ve bu üst bilgileri doğru sırada bulundurmamış olursunuz.

## <a name="the-global-namespace"></a>Genel ad alanı

Bir tanımlayıcı açık bir ad alanında bildirilirse, örtük genel ad alanının bir parçasıdır. Genel olarak, genel ad alanında olması gereken giriş noktası [ana işlevi](../c-language/main-function-and-program-execution.md)dışında, mümkün olduğunda genel kapsamda bildirim oluşturmaktan kaçınmaya çalışın. Genel tanımlayıcıyı açıkça nitelemek için, içinde `::SomeFunction(x);`olduğu gibi, ad olmadan kapsam çözümleme işlecini kullanın. Bu, tanımlayıcıyı diğer ad alanındaki aynı ada sahip herhangi bir şeyle ayırt eder ve ayrıca kodunuzun başkalarının anlaması için daha kolay hale getirmeye yardımcı olur.

## <a name="the-std-namespace"></a>std ad alanı

Tüm C++ standart kitaplık türleri ve işlevleri içinde `std` `std`iç içe yerleştirilmiş ad alanı veya ad alanlarında bildirilmiştir.

## <a name="nested-namespaces"></a>İç içe geçmiş ad alanları

Ad alanları iç içe olabilir. Sıradan iç içe yerleştirilmiş bir ad alanı, üst öğesinin üyelerine nitelenmemiş erişime sahiptir, ancak üst üyelerin, aşağıdaki örnekte gösterildiği gibi iç içe geçmiş ad alanına (satır içi olarak bildirildiği sürece) nitelenmemiş erişimi yoktur:

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

Sıradan iç içe geçmiş ad alanları, üst ad alanının genel arabiriminin parçası olmayan iç uygulama ayrıntılarını kapsüllemek için kullanılabilir.

## <a name="inline-namespaces-c-11"></a>Satır içi adC++ alanları (11)

Sıradan iç içe bir ad alanının aksine, bir satır içi ad alanının üyeleri üst ad alanının üyeleri olarak değerlendirilir. Bu özellik, aşırı yüklenmiş işlevlerde bağımsız değişken bağımlı aramanın üst ve iç içe geçmiş bir ad alanı üzerinde aşırı yüklerini olan işlevlerde çalışmasına olanak sağlar. Ayrıca, satır içi ad alanında belirtilen bir şablon için üst ad alanında bir özelleştirme bildirmenize olanak sağlar. Aşağıdaki örnek, dış kodun, varsayılan olarak satır içi ad alanına nasıl bağlanacağını göstermektedir:

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

Aşağıdaki örnek, bir satır içi ad alanında bildirimi olan bir şablonun üst öğesinde nasıl bir özelleştirme bildirekullanabileceğinizi göstermektedir:

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

Bir kitaplığın ortak arabirimindeki değişiklikleri yönetmek için, bir sürüm oluşturma mekanizması olarak satır içi ad alanları kullanabilirsiniz. Örneğin, tek bir üst ad alanı oluşturabilir ve arabirimin her bir sürümünü üst iç içe yerleştirilmiş kendi ad alanında kapsülleyebilirsiniz. En son veya tercih edilen sürümü tutan ad alanı satır içi olarak nitelenir ve bu nedenle, ana ad alanının doğrudan bir üyesi gibi gösterilir. Parent:: Class öğesini çağıran istemci kodu otomatik olarak yeni koda bağlanır. Eski sürümü kullanmayı tercih eden istemciler, bu koda sahip iç içe geçmiş ad alanının tam yolunu kullanarak buna erişmeye devam edebilir.

Satır içi anahtar sözcüğünün, bir derleme birimindeki ad alanının ilk bildirimine uygulanması gerekir.

Aşağıdaki örnek, her biri iç içe yerleştirilmiş bir ad alanında bir arabirimin iki sürümünü gösterir. Ad `v_20` alanı, `v_10` arabirimden bazı değişikliklere sahiptir ve satır içi olarak işaretlenir. Yeni kitaplığı ve çağrıları `Contoso::Funcs::Add` kullanan istemci kodu v_20 sürümünü çağıracaktır. Çağrı `Contoso::Funcs::Divide` yapmaya çalışacak kod şimdi bir derleme zamanı hatası alacak. Bu işleve gerçekten ihtiyaç duyuyorsanız, açıkça çağırarak `v_10` `Contoso::v_10::Funcs::Divide`sürüme erişmeye devam edebilirler.

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

## <a id="namespace_aliases"></a>Ad uzayı diğer adları

Ad alanı adlarının benzersiz olması gerekir. Bu, genellikle çok kısa olmaması gereken anlamına gelir. Bir adın uzunluğu kodu okumayı zorlaştırıyorsa veya kullanım yönergelerinin kullanılması gereken bir üst bilgi dosyasını yazmak sıkıcı ise, gerçek ad için bir kısaltma görevi gören bir ad alanı diğer adı yapabilirsiniz. Örneğin:

```cpp
namespace a_very_long_namespace_name { class Foo {}; }
namespace AVLNN = a_very_long_namespace_name;
void Bar(AVLNN::Foo foo){ }
```

## <a name="anonymous-or-unnamed-namespaces"></a>anonim veya adlandırılmamış ad alanları

Açık bir ad alanı oluşturabilirsiniz, ancak bunu bir ad veremezsiniz:

```cpp
namespace
{
    int MyFunc(){}
}
```

Bu adlandırılmamış veya anonim ad alanı olarak adlandırılır ve değişken bildirimlerini başka dosyalardaki koda görünmez hale getirmek istediğinizde (yani, iç bağlantı vermek) adlandırılmış bir ad alanı oluşturmaya gerek kalmadan yararlı olur. Aynı dosyadaki tüm kod tanımlayıcıları adlandırılmamış bir ad alanında görebilir, ancak ad alanının kendisi ile birlikte tanımlayıcılar bu dosyanın dışında görünmez veya çeviri biriminin dışında daha kesin bir şekilde görünür.

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimler ve Tanımlar](declarations-and-definitions-cpp.md)
