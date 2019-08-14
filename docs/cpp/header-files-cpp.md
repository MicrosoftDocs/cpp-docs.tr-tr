---
title: Üst bilgi dosyalarıC++()
ms.date: 04/20/2018
helpviewer_keywords:
- header files [C++]
ms.openlocfilehash: 98d37944f8c037f3ba25d80c7d35b3560ad11d40
ms.sourcegitcommit: db1ed91fa7451ade91c3fb76bc7a2b857f8a5eef
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/13/2019
ms.locfileid: "68980480"
---
# <a name="header-files-c"></a>Üst bilgi dosyalarıC++()

Değişkenler, işlevler, sınıflar vb. gibi program öğelerinin adları kullanılmadan önce bildirilmelidir. Örneğin, önce ' x ' bildirimini `x = 42` yapmadan yazmanız yeterlidir.

```cpp
int x; // declaration
x = 42; // use x
```

Bildirim, derleyiciye öğenin bir **int**, **Double**, bir **işlev**, bir **sınıf** veya başka bir şey olduğunu söyler.  Ayrıca, her bir ad, kullanıldığı her. cpp dosyasında bildirilmelidir (doğrudan veya dolaylı olarak). Bir program derlerken, her. cpp dosyası bir derleme birimine bağımsız olarak derlenir. Derleyicinin diğer derleme birimlerinde hangi adların bildirildiği hakkında hiçbir bilgisi yoktur. Diğer bir deyişle, bir sınıf veya işlev ya da genel değişken tanımlarsanız, onu kullanan her ek. cpp dosyasında bu şey için bir bildirim sağlamanız gerekir. Bu şeyi içeren her bildirim, tüm dosyalarda tam olarak özdeş olmalıdır. Bağlayıcı tüm derleme birimlerini tek bir programda birleştirmeye çalıştığında, hafif bir tutarsızlık hatalara veya istemeden davranışa neden olur.

Hata olasılığını en aza indirmek için, C++ *üst bilgi dosyalarını* kullanım kuralını bildirimleri içerecek şekilde benimseyin. Bildirimleri bir başlık dosyasında yapın, ardından her. cpp dosyasında veya bu bildirimi gerektiren diğer üstbilgi dosyasında #include yönergesini kullanın. #İnclude yönergesi, derleme öncesinde doğrudan. cpp dosyasına üstbilgi dosyasının bir kopyasını ekler.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir sınıfı bildirmek ve sonra farklı bir kaynak dosyasında kullanmak için ortak bir yol gösterir. Üst bilgi dosyası `my_class.h`ile başlayacağız. Sınıf tanımı içerir, ancak tanımın tamamlanmamış olduğunu unutmayın. üye işlevi `do_something` tanımlı değil:

```cpp
// my_class.h
namespace N
{
    class my_class
    {
    public:
        void do_something();
    };

}
```

Ardından, bir uygulama dosyası (genellikle bir. cpp veya benzer uzantı ile) oluşturun. My_class. cpp dosyasını çağıracak ve üye bildirimi için bir tanım sunacağız. My_class bildiriminin. `#include` cpp dosyasında bu noktada eklenmesini sağlamak için, "my_class. h" dosyası için bir yönerge ekledik ve bildirimini `std::cout`almak için dahil `<iostream>` ediyoruz. Tekliflerin, kaynak dosyayla aynı dizindeki üst bilgi dosyaları için kullanıldığını ve standart kitaplık üstbilgileri için açılı ayraçlar kullanıldığını unutmayın. Ayrıca, birçok standart kitaplık üstbilgisinde. h veya başka bir dosya uzantısı yoktur.

Uygulama dosyasında, "my_class" veya "cout" ifadesinin her birini "N::" ya da "std::" ile nitelendirmeyi önlemek için isteğe bağlı olarak bir **using** ifadesini kullanabiliriz.  Üst bilgi dosyalarınızda **using** deyimleri yerleştirmeyin!

```cpp
// my_class.cpp
#include "my_class.h" // header in local directory
#include <iostream> // header in standard library

using namespace N;
using namespace std;

void my_class::do_something()
{
    cout << "Doing something!" << endl;
}
```

Artık başka bir. `my_class` cpp dosyasında kullanabiliriz. Üst bilgi dosyasını derleyicinin bildirime çekmeleri için #include. Tüm derleyicisinin bilmelidir, my_class ortak üye işlevine `do_something()`sahip bir sınıftır.

```cpp
// my_program.cpp
#include "my_class.h"

using namespace N;

int main()
{
    my_class mc;
    mc.do_something();
    return 0;
}
```

Derleyici her. cpp dosyasını. obj dosyalarında derlemeyi tamamladıktan sonra,. obj dosyalarını bağlayıcıya geçirir. Bağlayıcı nesne dosyalarını birleşdiğinde, my_class için tam olarak bir tanım bulur; Bu, my_class. cpp için üretilen. obj dosyasında bulunur ve derleme başarılı olur.

## <a name="include-guards"></a>Koruyucuları dahil et

Genellikle, üst bilgi dosyalarında tek bir. cpp dosyasına `#pragma once` birden çok kez eklenmemesini sağlamak için bir *içerme koruyucusu* veya yönergesi bulunur.

```cpp
// my_class.h
#ifndef MY_CLASS_H // include guard
#define MY_CLASS_H

namespace N
{
    class my_class
    {
    public:
        void do_something();
    };
}

#endif /* MY_CLASS_H */
```

## <a name="what-to-put-in-a-header-file"></a>Üst bilgi dosyasına yerleştirilecek

Üst bilgi dosyası birden çok dosya tarafından bulunabilir olabileceği için, aynı ada sahip birden fazla tanım oluşturabilecek tanımlar içeremez. Aşağıdakilere izin verilmez veya çok hatalı uygulama olarak kabul edilir:

- ad alanı veya genel kapsamda yerleşik tür tanımları
- satır içi olmayan işlev tanımları
- const olmayan değişken tanımları
- Toplam tanımlar
- adlandırılmamış ad alanları
- using yönergeleri

**Using** yönergesinin kullanımı hataya neden olmaz, ancak ad alanını doğrudan veya dolaylı olarak bu üst bilgiyi içeren her. cpp dosyasında kapsama getiren bir soruna neden olabilir.

## <a name="sample-header-file"></a>Örnek üst bilgi dosyası

Aşağıdaki örnekte, bir üst bilgi dosyasında izin verilen çeşitli bildirim ve tanımlar gösterilmektedir:

```cpp
#pragma once
#include <vector> // #include directive
#include <string>

namespace N  // namespace declaration
{
    inline namespace P
    {
        //...
    }

    enum class colors : short { red, blue, purple, azure };

    const double PI = 3.14;  // const and constexpr definitions
    constexpr int MeaningOfLife{ 42 };
    constexpr int get_meaning()
    {
        static_assert(MeaningOfLife == 42, "unexpected!"); // static_assert
        return MeaningOfLife;
    }
    using vstr = std::vector<int>;  // type alias
    extern double d; // extern variable

#define LOG   // macro definition

#ifdef LOG   // conditional compilation directive
    void print_to_log();
#endif

    class my_class   // regular class definition,
    {                // but no non-inline function definitions

        friend class other_class;
    public:
        void do_something();   // definition in my_class.cpp
        inline void put_value(int i) { vals.push_back(i); } // inline OK

    private:
        vstr vals;
        int i;
    };

    struct RGB
    {
        short r{ 0 };  // member initialization
        short g{ 0 };
        short b{ 0 };
    };

    template <typename T>  // template definition
    class value_store
    {
    public:
        value_store<T>() = default;
        void write_value(T val)
        {
            //... function definition OK in template
        }
    private:
        std::vector<T> vals;
    };

    template <typename T>  // template declaration
    class value_widget;
}
```
