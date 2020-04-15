---
title: Üstbilgi dosyaları (C++)
ms.date: 12/11/2019
helpviewer_keywords:
- header files [C++]
ms.openlocfilehash: 4ab6a2b2626cde94f35678bc9ec789b80d493b8f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367241"
---
# <a name="header-files-c"></a>Üstbilgi dosyaları (C++)

Değişkenler, işlevler, sınıflar ve benzeri program öğelerinin adları kullanılmadan önce bildirilmelidir. Örneğin, 'x' bildirmeden `x = 42` yazamazsınız.

```cpp
int x; // declaration
x = 42; // use x
```

Bildirim derleyiciye öğenin bir **int,** **çift,** bir **işlev,** bir **sınıf** mı yoksa başka bir şey mi olduğunu söyler.  Ayrıca, her ad, kullanıldığı her .cpp dosyasında (doğrudan veya dolaylı olarak) bildirilmelidir. Bir program derlediğinizde, her .cpp dosyası bağımsız olarak bir derleme biriminde derlenir. Derleyicinin diğer derleme birimlerinde hangi adlar beyan edildiği hakkında hiçbir bilgisi yoktur. Bu, bir sınıf veya işlev veya genel değişken tanımlarsanız, o şeyin onu kullanan her ek .cpp dosyasında bir bildirim sağlamanız gerektiği anlamına gelir. O şeyin her bildirimi tüm dosyalarda tam olarak aynı olmalıdır. Bağlayıcı tüm derleme birimlerini tek bir programda birleştirmeye çalıştığında, küçük bir tutarsızlık hatalara veya istenmeyen davranışlara neden olur.

Hata potansiyelini en aza indirmek için, C++ bildirimleri içerecek *şekilde üstbilgi dosyalarını* kullanma kuralını benimsemiştir. Bildirimleri bir üstbilgi dosyasında yaparsınız, ardından #include yönergesini her .cpp dosyasında veya bu bildirimi gerektiren diğer üstbilgi dosyasında kullanırsınız. #include yönergesi, üstbilgi dosyasının bir kopyasını derlemeden önce doğrudan .cpp dosyasına ekler.

> [!NOTE]
> Visual Studio 2019'da C++20 *modülleri* özelliği, üstbilgi dosyalarının geliştirilmesi ve nihai yerine getirilmesi olarak tanıtıldı. Daha fazla bilgi için [C++ modüllerine genel bakış](modules-cpp.md)bölümüne bakın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir sınıfı bildirmek ve sonra farklı bir kaynak dosyada kullanmak için ortak bir yol gösterir. Üstbilgi dosyasıyla `my_class.h`başlayacağız. Bir sınıf tanımı içerir, ancak tanımının eksik olduğunu unutmayın; üye işlev `do_something` tanımlı değildir:

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

Ardından, bir uygulama dosyası (genellikle .cpp veya benzer bir uzantıyla) oluşturun. Dosyayı my_class.cpp olarak çağırır ve üye bildirimi için bir tanım sağlarız. my_class bildiriminin .cpp dosyasındaki bu noktada eklenmesi için "my_class.h" dosyası için `#include` `<iostream>` `std::cout`bir yönerge ekliyoruz ve beyannameye 'my_class.h" için bir yönerge ekliyoruz. Alıntıların kaynak dosyayla aynı dizindeki üstbilgi dosyaları için, açı ayraçlarının ise standart kitaplık üstbilgi için kullanıldığını unutmayın. Ayrıca, birçok standart kitaplık üstadı .h veya başka bir dosya uzantısı yok.

Uygulama dosyasında, isteğe bağlı olarak "my_class" veya "cout" ile "N::" veya "std::" ile her söz hak kazanmak zorunda önlemek için **bir kullanım** deyimi kullanabilirsiniz.  Üstbilgi dosyalarınızda ifadeleri **kullanmayın!**

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

Şimdi başka `my_class` bir .cpp dosyasında kullanabilirsiniz. Derleyicinin bildirimi çekmesi için üstbilgi dosyasını #include. Derleyicinin bilmesi gereken tek şey my_class'nin genel üye `do_something()`işlevi olan bir sınıf olduğudur.

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

Derleyici her .cpp dosyasını .obj dosyalarına derlemeyi bitirdikten sonra .obj dosyalarını bağlayıcıya geçirir. Bağlayıcı nesne dosyalarını birleştirdiğinde my_class için tam olarak bir tanım bulur; my_class.cpp için üretilen .obj dosyasında dır ve yapı başarılı olur.

## <a name="include-guards"></a>Korumaları dahil et

Genellikle, üstbilgi dosyaları, *include guard* tek bir `#pragma once` .cpp dosyasına birden çok kez eklenmediğinden emin olmak için bir dahil koruma veya yönergeye sahiptir.

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

## <a name="what-to-put-in-a-header-file"></a>Üstbilgi dosyasına ne konur

Üstbilgi dosyası birden çok dosya tarafından dahil edilebilir, çünkü aynı adın birden çok tanımı nı oluşturabilecek tanımlar içeremez. Aşağıdakilere izin verilmez veya çok kötü bir uygulama olarak kabul edilir:

- ad alanı veya genel kapsamda yerleşik tür tanımları
- satır içi olmayan işlev tanımları
- const olmayan değişken tanımları
- toplu tanımlar
- adlandırılmamış ad alanları
- direktifleri kullanarak

**Kullanım** yönergesinin kullanılması mutlaka bir hataya neden olmaz, ancak ad alanını doğrudan veya dolaylı olarak bu üstbilgiiçeren her .cpp dosyasında kapsamına getirdiğinden soruna neden olabilir.

## <a name="sample-header-file"></a>Örnek üstbilgi dosyası

Aşağıdaki örnek, üstbilgi dosyasında izin verilen çeşitli bildirim leri ve tanımları gösterir:

```cpp
// sample.h
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
