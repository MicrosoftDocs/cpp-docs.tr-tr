---
title: Üstbilgi dosyaları (C++) | Microsoft Docs
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
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b571cd2836e66ebef21898af27cf2a6d7082e0e5
ms.sourcegitcommit: d06966efce25c0e66286c8047726ffe743ea6be0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36238761"
---
# <a name="header-files-c"></a>Üstbilgi dosyaları (C++)

Değişkenler, İşlevler, sınıflar vb. gibi program öğelerinin adlarını kullanılabilmesi için önce bildirilmesi gerekir. Örneğin, yalnızca yazdığınız olamaz `x = 42` ilk 'x' bildirme olmadan. 

```cpp
int x; // declaration
x = 42; // use x
```

 Bildirimi derleyici olup olmadığını bildirir olan bir **int**, **çift**, **işlevi**, **sınıfı** veya başka bir şey.  Ayrıca, her bir adı (doğrudan veya dolaylı olarak) bu kullanıldığı her .cpp dosyasında bildirilmelidir. Bir program derlerken her .cpp dosya bağımsız olarak bir derleme birimine derlenir. Derleyici hangi adları diğer derleme birimlerinde bildirilir, hiçbir bilgiye sahiptir. Bir sınıf veya işlev veya genel değişkeni tanımlarsanız, o şey kullandığı her bir ek .cpp dosyadaki bildirimini sağlamalısınız anlamına gelir. Bu bir şey her bildirimi tüm dosyalarda tam olarak aynı olmalıdır. Tek bir program tüm derleme birimleri birleştirmek bağlayıcı denediğinde, hafif bir tutarsızlık hatalar veya beklenmedik davranışlara neden olur.

Hata olasılığını en aza indirmek için C++ kullanma kuralı benimsemiştir *üstbilgi dosyaları* bildirimleri içerecek şekilde. Üstbilgi dosyasında bildirimleri olun ve ardından kullanmak # her .cpp dosyasında include yönergesi veya diğer üstbilgi dosyası bu bildirimi gerektirir. # Doğrudan derleme önce .cpp dosyasına üstbilgi dosyasının bir kopyasını yönerge ekler include. 

## <a name="example"></a>Örnek

Aşağıdaki örnek bir sınıf bildirme ve farklı bir kaynak dosyasında kullanmak için en yaygın yolu gösterir. Üstbilgi dosyası ile başlayacağız **my_class.h**. Bir sınıf tanımını içerir, ancak tanımı eksik olduğunu unutmayın; üye işlevini `do_something` tanımlı değil:

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

Ardından, bir uygulama dosyası (genellikle bir .cpp veya benzer uzantısı ile) oluşturun. Biz dosya my_class.cpp çağırın ve üye bildirimi için bir tanım girin. Eklediğimiz bir `#include` yönerge eklenen my_class bildirimi olması için "my_class.h" dosyası için bu noktada .cpp dosya ve biz dahil  **\<iostream >** bildirimi çekmesini `std::cout`. Tırnak işaretleri üstbilgi dosyaları kaynak dosya ile aynı dizinde için kullanılır ve standart kitaplığı üstbilgilerini köşeli kullanılır unutmayın. Ayrıca, birçok standart kitaplık üstbilgi .h veya herhangi bir dosya uzantısına sahip.

Uygulama dosyasında biz isteğe bağlı olarak kullanabilirsiniz bir **kullanarak** ile her Bahsetme "my_class" veya "cout" nitelemek zorunda kalmamak için deyimi "N::" veya "std::".  Koymayın **kullanarak** başlık dosyalarının deyimlerinde!

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

Artık biz kullanarak `my_class` başka bir .cpp dosyasında. Sizi # üstbilgi dosyası include derleyici bildiriminde çeker. Bilmeniz tüm derleyici gereksinimlerini olduğundan bu my_class adında bir ortak üye işlevi olan bir sınıfı olan `do_something()`.

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

.Obj dosyaları içine her .cpp dosyasını derleme derleyici bittikten sonra bağlayıcıya .obj dosyaları geçirir. Nesne dosyaları bağlayıcı birleştirmesi durumunda my_class için tam olarak bir tanım bulur; my_class.cpp için üretilen .obj dosyasında olduğunu ve derleme başarılı olur.

## <a name="include-guards"></a>Koruyucuları içerir

Genellikle, üst bilgi dosyalarınız bir *koruma dahil* veya **#pragma kez** yönergesi bunlar birden çok kez tek .cpp dosyasına eklenmiyor emin olun. 

my_class.h
#<a name="ifndef-myclassh--include-guard"></a>ıfndef MY_CLASS_H / / guard içerir
#<a name="define-myclassh"></a>MY_CLASS_H tanımlayın


ad alanı N {sınıf my_class {ortak: do_something(); void};

}

#<a name="endif--myclassh-"></a>endif / * MY_CLASS_H * /

## <a name="what-to-put-in-a-header-file"></a>Üstbilgi dosyasında put gerekenler

Üstbilgi dosyası büyük olasılıkla tarafından birden çok dosya eklenebilir olduğundan, aynı adlı birden fazla tanımı üretebilir tanımları içeremez. Aşağıdaki izin verilmeyen veya çok hatalı yöntem olarak kabul edilir:

- ad alanı veya genel kapsam yerleşik tür tanımları
- Satır içi olmayan işlev tanımları 
- const olmayan değişken tanımları
- Birleşik tanımları
- adlandırılmamış ad alanları
- using yönergelerini

Kullanımı **kullanarak** yönergesi mutlaka bir hata neden olmayacak, ancak bu ad alanı doğrudan veya dolaylı olarak bu başlığı içeren her .cpp dosyası kapsamda getirir çünkü bir soruna neden olabilir. 

## <a name="sample-header-file"></a>Örnek üstbilgi dosyası

Aşağıdaki örnek, çeşitli bildirimler ve bir üstbilgi dosyasında izin verilen tanımlar gösterir:

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
