---
title: Derleyici Hatası C2065
ms.date: 09/01/2017
f1_keywords:
- C2065
helpviewer_keywords:
- C2065
ms.assetid: 78093376-acb7-45f5-9323-5ed7e0aab1dc
ms.openlocfilehash: 3daf2cd532cd07225b822c80b46fc28274d4e2a8
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59779407"
---
# <a name="compiler-error-c2065"></a>Derleyici Hatası C2065

> '*tanımlayıcı*': bildirimi yapılmamış tanımlayıcı

Derleyici, tanımlayıcının bildirimi bulunamıyor. Bu hata birçok olası nedeni vardır. C2065 en yaygın nedenlerini tanımlayıcı bildirilmeyen, tanımlayıcı yanlış yazılmış, tanımlayıcı burada bildirilir üst bilgi dosyasında yer almayan veya tanımlayıcısı kapsam niteleyicisi, örneğin, eksik emin olan `cout` yerine `std::cout`. C++'ta bildirimleri hakkında daha fazla bilgi için bkz. [bildirimleri ve tanımları (C++)](../../cpp/declarations-and-definitions-cpp.md).

Daha ayrıntılı olarak bazı yaygın sorunlar ve çözümleri şunlardır.

## <a name="the-identifier-is-undeclared"></a>Bildirilmemiş tanımlayıcı

Tanımlayıcı, bir değişken veya işlev adının ise, kullanılmadan önce bildirmelidir. İşlevi kullanılmadan önce bir işlev bildirimi parametrelerinin türleri de içermelidir. Değişkeni kullanılarak bildirilirse `auto`, derleyici Başlatıcısı türü belirleyebilir.

Tanımlayıcısını bir sınıf veya yapı üyesi veya bir ad alanı bildirimi, bu sınıf veya yapı adı veya ad alanı adı yapı, sınıf veya ad alanı kapsamı dışında kullanıldığında nitelenmelidir. Alternatif olarak, ad alanı tarafından kapsama getirilmesi gereken bir `using` gibi yönerge `using namespace std;`, veya üye adıyla kapsama göre getirilmesi gereken bir `using` bildirimi gibi `using std::string;`. Aksi takdirde, nitelenmemiş ad geçerli kapsamda bildirilmemiş tanımlayıcı olarak kabul edilir.

Tanımlayıcı etiketi için bir kullanıcı tanımlı tür, örneğin, ise bir `class` veya `struct`, kullanılmadan önce etiket türü bildirilmesi gerekir. Örneğin, bildirimi `struct SomeStruct { /*...*/ };` bir değişken bildirmek önce mevcut olması `SomeStruct myStruct;` kodunuzda.

Tanımlayıcı bir tür diğer adı ise, türü kullanılarak bildirilmelidir bir `using` bildirimi veya `typedef` kullanılmadan önce. Örneğin, bildirmelisiniz `using my_flags = std::ios_base::fmtflags;` kullanabilmeniz için önce `my_flags` için bir tür diğer adı olarak `std::ios_base::fmtflags`.

## <a name="example-misspelled-identifier"></a>Örnek: yanlış yazılmış tanımlayıcısı

Bu hata genellikle tanımlayıcı adı yanlış yazılmış veya yanlış büyük ve küçük harfler tanımlayıcısını kullanır oluşur. Adın bildiriminde kullandığınız adı tam olarak eşleşmelidir.

```cpp
// C2065_spell.cpp
// compile with: cl /EHsc C2065_spell.cpp
#include <iostream>
using namespace std;
int main() {
    int someIdentifier = 42;
    cout << "Some Identifier: " << SomeIdentifier << endl;
    // C2065: 'SomeIdentifier': undeclared identifier
    // To fix, correct the spelling:
    // cout << "Some Identifier: " << someIdentifier << endl;
}
```

## <a name="example-use-an-unscoped-identifier"></a>Örnek: kapsamsız bir tanımlayıcı kullanın

Bu hata, tanımlayıcısı olmayan düzgün kapsamlıdır ortaya çıkabilir. Kullanırken C2065 görürseniz `cout`, nedeni budur. C++ Standart Kitaplığı işlevleri ve işleçleri değil tam nitelenmiş ad alanı tarafından veya değil getirdiğiniz `std` ad alanına kullanarak geçerli kapsamdaki bir `using` yönergesi, derleyici bunları bulamıyoruz. Bu sorunu gidermek için tam olarak Sınıflandır tanımlayıcı adları, veya ad alanıyla belirtin `using` yönergesi.

Bu örnekte derlenemiyor çünkü `cout` ve `endl` tanımlanan `std` ad alanı:

```cpp
// C2065_scope.cpp
// compile with: cl /EHsc C2065_scope.cpp
#include <iostream>
// using namespace std;   // Uncomment this line to fix

int main() {
    cout << "Hello" << endl;   // C2065 'cout': undeclared identifier
                               // C2065 'endl': undeclared identifier
    // Or try the following line instead
    std::cout << "Hello" << std::endl;
}
```

İçinde bildirilmiş olan tanımlayıcıları `class`, `struct`, veya `enum class` türleri de nitelenmiş kapsayan kapsamından adına göre bu kapsamı dışında kullandığınızda.

## <a name="example-precompiled-header-isnt-first"></a>Örnek: önceden derlenmiş üst bilgi ilk değil

Tüm önişlemci yönergeleri gibi koyarsanız bu hata oluşabilir #include #define veya #pragma, önce #include önceden derlenmiş üst bilgi dosyası. Kaynak dosyanıza bir ön derlenmiş üstbilgi dosyası kullanıyorsa (diğer bir deyişle, onu kullanarak derlenirse **/Yu** derleyici seçeneği) sonra tüm önişlemci yönergeleri önce önceden derlenmiş üstbilgi dosyasını göz ardı edilir.

Bu örnekte derlenemiyor çünkü `cout` ve `endl` tanımlanan \<iostream > önce önceden derlenmiş üst bilgi dosyasını dahil olduğundan sayılan başlığı. Bu örneği oluşturmak için üç dosya oluşturma sonra stdafx.cpp derleme C2065_pch.cpp derleyin.

```cpp
// stdafx.h
#include <stdio.h>
```

```cpp
// stdafx.cpp
// Compile by using: cl /EHsc /W4 /c /Ycstdafx.h stdafx.cpp
#include <stdafx.h>
```

```cpp
// C2065_pch.cpp
// compile with: cl /EHsc /W4 /Yustdafx.h C2065_pch.cpp
#include <iostream>
#include "stdafx.h"
using namespace std;

int main() {
    cout << "Hello" << endl;   // C2065 'cout': undeclared identifier
                               // C2065 'endl': undeclared identifier
}
```

Bu sorunu gidermek için Ekle #, include \<iostream > Ön derlenmiş üstbilgi dosyası ya da Taşı sonra önceden derlenmiş üstbilgi dosyasının kaynak dosyanıza eklenir.

## <a name="example-missing-header-file"></a>Örnek: üst bilgi dosyası eksik.

Tanımlayıcı bildiren üstbilgi dosyasını dahil değildir. Tanımlayıcı için bildirimi içeren dosyanın kullandığı her bir kaynak dosyasında bulunduğundan emin olun.

```cpp
// C2065_header.cpp
// compile with: cl /EHsc C2065_header.cpp

//#include <stdio.h>
int main() {
    fpos_t file_position = 42; // C2065: 'fpos_t': undeclared identifier
    // To fix, uncomment the #include <stdio.h> line
    // to include the header where fpos_t is defined
}
```

Başlatıcı listesi dahil etmeden kullanırsanız başka bir olası neden olduğu \<initializer_list > Üstbilgi.

```cpp
// C2065_initializer.cpp
// compile with: cl /EHsc C2065_initializer.cpp

// #include <initializer_list>
int main() {
    for (auto strList : {"hello", "world"})
        if (strList == "hello") // C2065: 'strList': undeclared identifier
            return 1;
    // To fix, uncomment the #include <initializer_list> line
}
```

Tanımlarsanız, Windows Masaüstü uygulama kaynak dosyalarında bu hatayı görebilirsiniz `VC_EXTRALEAN`, `WIN32_LEAN_AND_MEAN`, veya `WIN32_EXTRA_LEAN`. Bu Önişlemci makroları bazı başlık dosyalarını windows.h afxv dışında tutma ve\_w32.h hızlandırmak için derler. Windows.h ve dışarıda bırakıldı güncel bir açıklaması için afxv_w32.h bakın.

## <a name="example-missing-closing-quote"></a>Örnek: kapatma tırnağı eksik.

Bu hata, bir dize sabitine sonra bir kapatma tırnağı eksikse oluşabilir. Bu, derleyicinin karıştırmak için kolay bir yoludur. Eksik kapatma tırnağı önce bildirilen hatayı konumu birden fazla satır olabileceğine dikkat edin.

```cpp
// C2065_quote.cpp
// compile with: cl /EHsc C2065_quote.cpp
#include <iostream>

int main() {
    // Fix this issue by adding the closing quote to "Aaaa"
    char * first = "Aaaa, * last = "Zeee";
    std::cout << "Name: " << first
        << " " << last << std::endl; // C2065: 'last': undeclared identifier
}
```

## <a name="example-use-iterator-outside-for-loop-scope"></a>Örnek: dışında yineleyici döngü kapsamı için kullanın.

Bir yineleyici değişkeninde bildirirseniz bu hata oluşabilir bir `for` döngü ve daha sonra deneyin yineleyici değişken kapsamı dışında kullanmak `for` döngü. Derleyiciyi etkinleştirir [/ZC: forscope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) varsayılan olarak derleyici seçeneği. Bkz: [Debug Iterator Support](../../standard-library/debug-iterator-support.md) daha fazla bilgi için.

```cpp
// C2065_iter.cpp
// compile with: cl /EHsc C2065_iter.cpp
#include <iostream>
#include <string>

int main() {
    // char last = '!';
    std::string letters{ "ABCDEFGHIJKLMNOPQRSTUVWXYZ" };
    for (const char& c : letters) {
        if ('Q' == c) {
            std::cout << "Found Q!" << std::endl;
        }
        // last = c;
    }
    std::cout << "Last letter was " << c << std::endl; // C2065
    // Fix by using a variable declared in an outer scope.
    // Uncomment the lines that declare and use 'last' for an example.
    // std::cout << "Last letter was " << last << std::endl; // C2065
}
```

## <a name="example-preprocessor-removed-declaration"></a>Örnek: önişlemci kaldırılan bildirimi

Bir işlev veya geçerli yapılandırmanız için derlenmedi koşullu olarak derlenmiş kodda olan değişken başvuruyorsa, bu hata oluşabilir. Derleme ortamınızda şu anda desteklenmeyen bir üstbilgi dosyasında bir işlev çağırırsanız de oluşabilir. Belirli önişlemci makrosu tanımlandığında belirli değişkenleri ve işlevleri yalnızca kullanamıyorsanız, aynı önişlemci makrosu tanımlandığında, yalnızca bu işlevleri çağıran kodu derlenebilir olduğundan emin olun. Geçerli derleme yapılandırması için gerekli Önişlemci makroları tanımlı değil, işlev bildirimi devre dışı olduğundan bu sorun IDE içindeki nokta için kolay bir işlemdir.

Bu, hata ayıklama yapısında, ancak değil perakende çalışan bir kod örneğidir:

```cpp
// C2065_defined.cpp
// Compile with: cl /EHsc /W4 /MT C2065_defined.cpp
#include <iostream>
#include <crtdbg.h>
#ifdef _DEBUG
    _CrtMemState oldstate;
#endif
int main() {
    _CrtMemDumpStatistics(&oldstate);
    std::cout << "Total count " << oldstate.lTotalCount; // C2065
    // Fix by guarding references the same way as the declaration:
    // #ifdef _DEBUG
    //    std::cout << "Total count " << oldstate.lTotalCount;
    // #endif
}
```

## <a name="example-ccli-type-deduction-failure"></a>Örnek: C++/ CLI tür kesintisi hatası

Hedeflenen tür bağımsız değişkeni kullanılan parametreler küçültülürse genel bir işlev çağrılırken bu hata oluşabilir. Daha fazla bilgi için [genel işlevler (C++/CLI)](../../extensions/generic-functions-cpp-cli.md).

```cpp
// C2065_b.cpp
// compile with: cl /clr C2065_b.cpp
generic <typename ItemType>
void G(int i) {}

int main() {
   // global generic function call
   G<T>(10);     // C2065
   G<int>(10);   // OK - fix with a specific type argument
}
```

## <a name="example-ccli-attribute-parameters"></a>Örnek: C++/ CLI öznitelik parametreleri

Bu hata için Visual C++ 2005 yapıldığı derleyici uyumluluğu iş sonucu olarak da oluşturulabilir: Visual C++ öznitelikleri için parametre.

```cpp
// C2065_attributes.cpp
// compile with: cl /c /clr C2065_attributes.cpp
[module(DLL, name=MyLibrary)];   // C2065
// try the following line instead
// [module(dll, name="MyLibrary")];

[export]
struct MyStruct {
   int i;
};
```
