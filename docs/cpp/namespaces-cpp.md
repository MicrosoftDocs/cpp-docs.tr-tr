---
title: Ad Alanları (C++)
ms.date: 08/30/2017
f1_keywords:
- namespace_CPP
- using_CPP
helpviewer_keywords:
- namespaces [C++]
ms.assetid: d1a5a9ab-1cad-47e6-a82d-385bb77f4188
ms.openlocfilehash: 15717c6f2f34836de9b546af203a45dc8099d4d4
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222358"
---
# <a name="namespaces-c"></a>Ad Alanları (C++)

Bir ad alanı içindeki tanımlayıcıları (adları türler, İşlevler, değişkenler vb.) için bir kapsam sağlayan tanımlayıcı bir bölgedir. Ad alanlarında, kod mantıksal gruplar halinde düzenlemek ve özellikle kod tabanınızın birden çok kitaplık içerdiğinde oluşabilecek ad çakışmalarını önlemek için kullanılır. Ad alanı kapsamında tüm tanımlayıcılar niteleme olmadan bir başkasına görünür. Tanımlayıcı ad alanı dışında her tanımlayıcısı için tam adı örneğin kullanarak üyeleri erişebilir `std::vector<std::string> vec;`, göre veya başka bir [using bildirimi](../cpp/using-declaration.md) tek bir tanımlayıcı için (`using std::string`), veya bir [using yönergesi](../cpp/namespaces-cpp.md#using_directives) ad alanındaki tüm tanımlayıcıları için (`using namespace std;`). Üst bilgi dosyaları içindeki kod her zaman tam olarak nitelenmiş ad alanı adı kullanmanız gerekir.

Aşağıdaki örnek, bir ad alanı bildirimi gösterir ve ad alanı dışında kod üç yolu üyeleri erişir.

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

Tam adını kullanın:

```cpp
ContosoData::ObjectManager mgr;
mgr.DoSomething();
ContosoData::Func(mgr);
```

Bir using bildirimi bir tanımlayıcı kapsama alınmak üzere:

```cpp
using ContosoData::ObjectManager;
ObjectManager mgr;
mgr.DoSomething();
```

Bir using yönergesi her şeyi ad alanında kapsama alınmak üzere:

```cpp
using namespace ContosoData;

ObjectManager mgr;
mgr.DoSomething();
Func(mgr);
```

## <a id="using_directives"></a> using yönergeleri

**Kullanarak** yönergesi verir bölgedeki tüm adları bir **ad alanı** olmadan kullanılacak *ad alanı adı* açık Niteleyici olarak. Bir using birkaç farklı tanımlayıcı bir ad alanında; kullanıyorsanız, yönerge bir uygulama dosyasında (yani, *.cpp) bir veya iki tanımlayıcıları yeni kullanıyorsanız, kullanarak bir göz önünde bulundurun yalnızca bu tanımlayıcıları ad alanında kapsamı ve tüm tanımlayıcılar getirmek için bildirimi. Yerel bir değişken adı ad alanı değişkeniyle aynı ada sahipse, ad alanı değişkeni gizlenir. Genel bir değişken olarak aynı ada sahip ad alanı değişkeninin bulundurulması bir hatadır.

> [!NOTE]
>  Using yönergesi (Dosya kapsamında), .cpp dosyasının üst yerleştirilebilir ya da bir sınıf veya işlev tanımı içinde.
>
>  Genel olarak, üst bilgi dosyaları yönergeleri kullanarak Geçirilmemesi (* .h), üst bilgi içeren herhangi bir dosyayı her şeyi ad alanında kapsamına getirir çünkü hangi ad gizleme ve neden olabilir, çakışma sorunları ad hata ayıklamak oldukça zor. Her zaman bir üstbilgi dosyasında tam olarak nitelenmiş adlar kullanın. Bu ad çok uzun alırsanız, bunları kısaltmak için bir ad alanı diğer adlarını kullanabilirsiniz. (Aşağıya bakın.)

## <a name="declaring-namespaces-and-namespace-members"></a>Ad alanları ve ad alanı üyeleri bildirme

Genellikle bir üstbilgi dosyasında bir ad alanı bildirin. Ardından, işlev uygulamaları içinde ayrı bir dosya varsa, bu örnekte olduğu gibi işlev adlarını nitelendirin.

```cpp
//contosoData.h
#pragma once
namespace ContosoDataServer
{
    void Foo();
    int Bar();
}
```

Contosodata.cpp işlevi uygulamalarında yerleştirdiğiniz olsa bile tam nitelikli ad kullanması gereken bir **kullanarak** dosyasının en üstüne yönergenizi:

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

Bir ad alanı, tek bir dosyada ve birden çok dosya birden çok bloğundaki bildirilebilir. Ön işleme sırasında birlikte derleyici parçaları birleştirir ve elde edilen ad alanı tüm bölümleri bildirilen tüm üyeleri içerir. Buna örnek olarak, her bir standart kitaplık üstbilgi dosyalarında bildirilen std ad alanıdır.

Adlandırılmış bir ad alanının üyeleri, tanımlanan adın açık nitelik tarafından bildirilen ad alanının dışında tanımlanabilir. Ancak tanımın, bildirimin ad alanını kapsayan bir ad alanında bildirim noktasından sonra görünmesi gerekir. Örneğin:

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
}
```

Namespace üyelerini birden çok üst bilgi dosyaları arasında bildirilir ve doğru sırada bu üstbilgileri eklemediniz bu hata oluşabilir.

## <a name="the-global-namespace"></a>Genel ad alanı

Bir tanımlayıcı, açık bir ad alanında bildirilmedi varsa örtük genel ad alanı bir parçasıdır. Genel olarak, mümkün olduğunda, giriş noktası hariç olmak üzere genel kapsamda bildirimleri yapma kaçınmaya çalışın [main işlevi](../c-language/main-function-and-program-execution.md), genel ad alanında olması gerekir. Genel tanımlayıcı açıkça nitelemek için olarak adı olmayan bir kapsam çözümleme işleci kullanın `::SomeFunction(x);`. Başka bir ad alanında aynı ada sahip bir yerden bu tanımlayıcıyı yaratabilmelerini sağlayacak ve ayrıca kodunuzu başkalarının anlamak daha kolay hale getirmek için yardımcı olur.

## <a name="the-std-namespace"></a>std ad alanı

İçinde bildirilen tüm C++ standart kitaplık türleri ve işlevleri `std` ad alanı veya ad alanlarında iç içe geçmiş içinde `std`.

## <a name="nested-namespaces"></a>İç içe geçmiş ad alanları

Ad alanlarında iç içe. Sıradan bir iç içe geçmiş ad alanına sahip üst öğesinin üyeleri, ancak üst üyelerinin nitelenmemiş erişimi nitelenmemiş erişim sahibi iç içe geçmiş ad alanı (satır içi olarak bildirildiği sürece), aşağıdaki örnekte gösterildiği gibi:

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

Sıradan iç içe geçmiş ad alanları, üst ad alanında'nın ortak arabiriminin bir parçası olmayan iç uygulama ayrıntılarını kapsüllemek için kullanılabilir.

## <a name="inline-namespaces-c-11"></a>Satır içi ad alanları (C++ 11)

Sıradan bir iç içe geçmiş ad aksine, bir satır içi ad alanının üyeleri, üst ad alanında bir üyesi olarak kabul edilir. Bu özellik, bir üst öğe ve bir iç içe geçmiş satır içi ad alanı içinde aşırı olan işlevler üzerinde çalışmak için aşırı yüklenmiş işlevlerdeki bağımsız değişken bağımlı aramayı etkinleştirir. Ayrıca, bir üst ad alanında satır içi ad alanında bildirilen bir şablonunun bir özelleştirmesi bildirmek sağlar. Aşağıdaki örnek, nasıl harici kod gösterir. varsayılan olarak satır içi ad alanına bağlar:

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

Aşağıdaki örnek, bir özelleştirmede üst öğesi bir satır içi ad alanında bildirilen bir şablonun nasıl bildirebilirsiniz gösterir:

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

Sürüm oluşturma mekanizması olarak satır içi ad alanları, bir kitaplık ortak arabiriminde değişiklikleri yönetmek için kullanabilirsiniz. Örneğin, tek üst ad alanı oluşturma ve üst içinde iç içe geçmiş kendi ad alanı arabiriminde'nün her sürümü kapsüller. En son veya tercih edilen sürümü içeren ad alanı satır içi olarak tam ve ana ad uzayını doğrudan üyesi değilmiş gibi bu nedenle sunulur. Parent::Class çağıran istemci kodu yeni kodu otomatik olarak bağlanır. Eski sürümü kullanmayı tercih istemciler, bu kodu olan iç içe geçmiş ad alanı için tam yol kullanarak erişmeye devam edebilir.

İnline anahtar sözcüğü, bir derleme biriminde ad alanının ilk bildirimi için uygulanması gerekir.

Aşağıdaki örnek bir arabirim, her bir iç içe geçmiş ad alanında iki sürümünü gösterir. `v_20` Ad alanına sahip bazı değişikliklere karşı `v_10` arabirim ve satır içi olarak işaretlenir. Aramalar ve yeni bir kitaplık kullanan istemci kodu `Contoso::Funcs::Add` v_20 sürüm çağırır. Çağırmak için çalışan kod `Contoso::Funcs::Divide` artık bir derleme zamanı hatası alırsınız. Bu işlev, gerçekten ihtiyacınız varsa, yine de erişebilmeleri `v_10` açıkça çağırarak sürüm `Contoso::v_10::Funcs::Divide`.

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

## <a id="namespace_aliases"></a> Namespace diğer adları

Namespace adlarının benzersiz olması genellikle bunlar çok kısa olmamalıdır, yani gerekir. Kod bir adının uzunluğu okumak zor yaparsa veya burada yönergeleri kullanarak kullanılamaz ve ardından gerçek adı için bir kısaltma olarak hizmet veren bir ad alanı diğer adı yapabileceğiniz bir üstbilgi dosyasında tür yorucu olabilir. Örneğin:

```cpp
namespace a_very_long_namespace_name { class Foo {}; }
namespace AVLNN = a_very_long_namespace_name;
void Bar(AVLNN::Foo foo){ }
```

## <a name="anonymous-or-unnamed-namespaces"></a>anonim veya adlandırılmamış ad alanları

Açık bir ad alanı oluşturun, ancak bir ad verin değil:

```cpp
namespace
{
    int MyFunc(){}
}
```

Bu adlandırılmamış ya da anonim bir ad alanı adı verilir ve değişken bildirimleri diğer dosyalar için kod görünmez yapmak istediğinizde yararlı olur (yani iç bağlantı vermediğiniz) adlı bir ad alanı oluşturmak zorunda kalmadan. Aynı dosyadaki tüm kod adlandırılmamış bir ad alanı tanımlayıcılarını görebilir, ancak ad alanı kendisini yanı sıra tanımlayıcıların, bu dosyanın dışında görünür değildir — veya çeviri biriminde dışında daha kesin.

## <a name="see-also"></a>Ayrıca bkz.

[Bildirimler ve Tanımlar](declarations-and-definitions-cpp.md)