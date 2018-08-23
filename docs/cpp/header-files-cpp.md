---
title: Üst bilgi dosyaları (C++) | Microsoft Docs
ms.custom: ''
ms.date: 04/20/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- header files [C++]
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: be194095b6461eaedd9e814c6130801b431fef5d
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42602419"
---
# <a name="header-files-c"></a>Üst bilgi dosyaları (C++)

Değişkenler, İşlevler, sınıflar ve benzeri gibi program öğelerinin adlarını kullanılabilmesi için önce bildirilmelidir. Örneğin, yalnızca yazdığınız olamaz `x = 42` ilk bildirme 'x' olmadan. 

```cpp
int x; // declaration
x = 42; // use x
```

 Bildirimi mi derleyiciye olduğu bir **int**, **çift**, **işlevi**, **sınıfı** veya başka bir şey.  Ayrıca, her adı (doğrudan veya dolaylı olarak), kullanıldığı her .cpp dosyasında bildirilmelidir. Bir program derlediğinizde, her .cpp dosyası bir derleme birimine bağımsız olarak derlenir. Derleyici, diğer derleme biriminde bildirilen hangi adlar, hiçbir bilgiye sahiptir. Bir sınıf veya işlev ya da genel değişken tanımlarsanız, bu şeyi kullandığı her ek .cpp dosyası bildirimi sağlamalısınız anlamına gelir. Her şey bu bildirimi tüm dosyaların tam olarak aynı olmalıdır. Bağlayıcı, tüm derleme biriminden tek bir programa birleştirme girişiminde bulunduğunda hafif bir tutarsızlık hataları veya beklenmedik davranışlara neden olur.

Hataları olasılığını en aza indirmek için C++ kullanarak kuralı başlamıştır *üst bilgi dosyaları* bildirimleri içerecek. Bir üstbilgi dosyasında bildirimleri olun, ardından kullanmak #include yönergesi her .cpp dosyası içinde veya diğer üst bilgi dosyası bu bildirimi gerektirir. # Yönergesi ekler, .cpp dosyası derleme önce doğrudan üst bilgi dosyasının bir kopyasını include. 

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir sınıf bildirme ve ardından farklı bir kaynak dosyada kullanmak için en yaygın yolu gösterir. Üst bilgi dosyası ile başlayacağız `my_class.h`. Bir sınıfı tanım içeriyor, ancak tanımı eksik olduğunu unutmayın; üye işlevi `do_something` tanımlı değil:

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

Ardından, bir uygulama dosyasını (genellikle bir .cpp veya benzer genişletme ile) oluşturun. Biz dosya my_class.cpp çağırın ve üye bildirimi için bir tanım girin. Eklediğimiz bir `#include` yönerge eklenen my_class bildirimi sahip olmak için "my_class.h" dosyası için bu noktada .cpp dosyası ve biz dahil `<iostream>` bildirimi sütunlarından `std::cout`. Tırnak işaretleri kaynak dosyayla aynı dizinde üst bilgi dosyaları için kullanılır ve açılı ayraçlar standart kitaplığı üst bilgileri için kullanılan unutmayın. Ayrıca, birçok standart kitaplık üstbilgi .h veya başka bir dosya uzantısına sahip değilsiniz.

V souboru implementace, isteğe bağlı olarak kullanabiliriz bir **kullanarak** deyimi ile her Bahsetme "my_class" veya "cout" uygun olmamasına özen gösterin "N::" veya "std::".  Koymayın **kullanarak** üstbilgi dosyalarınızın deyimlerinde!

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

Kullanabiliriz artık `my_class` başka bir .cpp dosyası içinde. Biz # üstbilgi dosyasını include derleyici bildiriminde çeker. Bilmeniz gereken tüm derleyici gereksinimlerini olan bu my_class adlı bir ortak üye işleve sahip bir sınıfı olan `do_something()`.

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

Derleyici .cpp dosyası her .obj dosyasına derleme tamamlandıktan sonra .obj dosyaları bağlayıcıya iletir. Nesne dosyalarının bağlayıcı birleştiği my_class için tam olarak bir tanımı bulur; my_class.cpp için üretilmiş .obj dosyasındaki olduğunu ve derleme başarılı olur.

## <a name="include-guards"></a>Cf içerir

Genellikle, üst bilgi dosyalarınız bir *guard dahil* veya `#pragma once` bunlar birden çok kez tek .cpp dosyasına eklenmiyor emin olmak için yönergesi. 

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

## <a name="what-to-put-in-a-header-file"></a>Bir üstbilgi dosyasında konulacaklar

Bir üstbilgi dosyası potansiyel olarak birden çok dosya tarafından eklenmiş olabilir çünkü bu, aynı ada sahip birden çok tanım üretebilir tanımları içeremez. Aşağıdaki izin verilmeyen veya çok hatalı bir uygulama olarak kabul edilir:

- ad alanı veya genel kapsamlı yerleşik tür tanımları
- Satır içi işlev tanımları 
- const olmayan değişken tanımları
- Toplama tanımları
- adlandırılmamış ad alanları
- using yönergeleri

Kullanım **kullanarak** yönergesi mutlaka hataya neden olmaz, ancak bu ad alanı kapsamında doğrudan veya dolaylı olarak söz konusu üst bilgisi içeren her .cpp dosyası getirir çünkü bir soruna neden olabilir. 

## <a name="sample-header-file"></a>Örnek üst bilgi dosyası

Aşağıdaki örnek, çeşitli üstbilgi dosyasında verilen tanımları ve bildirimleri gösterir:

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