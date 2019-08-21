---
title: Derleyici hatası C2065
ms.date: 08/19/2019
f1_keywords:
- C2065
helpviewer_keywords:
- C2065
ms.assetid: 78093376-acb7-45f5-9323-5ed7e0aab1dc
ms.openlocfilehash: 40d1d0744588c4b7911e84f5e57a6b40372b48cf
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/20/2019
ms.locfileid: "69630128"
---
# <a name="compiler-error-c2065"></a>Derleyici hatası C2065

> '*tanımlayıcı*': bildirilmemiş tanımlayıcı

Derleyici bir tanımlayıcı için bildirimi bulamıyor. Bu hatanın birçok olası nedeni vardır. C2065 'in en yaygın nedenleri, tanımlayıcının bildirilmediği, tanımlayıcının yanlış yazılabileceği, tanımlayıcının bildirildiği üstbilginin dosyaya dahil olmadığı veya tanımlayıcıda bir kapsam niteleyicisi eksik olduğu, örneğin `cout` yerine `std::cout`. İçindeki C++bildirimler hakkında daha fazla bilgi için bkz. [Bildirimler ve tanımlarC++()](../../cpp/declarations-and-definitions-cpp.md).

Daha ayrıntılı olarak bazı yaygın sorunlar ve çözümler aşağıda verilmiştir.

## <a name="the-identifier-is-undeclared"></a>Tanımlayıcı bildirilmemiş

Tanımlayıcı bir değişken veya işlev adı ise, kullanılmadan önce bunu bildirmeniz gerekir. İşlev bildirimi, işlev kullanılmadan önce parametrelerinin türlerini de içermelidir. Değişken kullanılarak `auto`bildirilirse, derleyicinin türü başlatıcıdan çıkarsanbiliyor olması gerekir.

Tanımlayıcı bir sınıfın veya yapının üyesiyse veya bir ad alanında bildirilirse, yapı, sınıf veya ad alanı kapsamı dışında kullanıldığında sınıf veya yapı adı ya da ad alanı adı tarafından nitelenmelidir. Alternatif olarak, ad alanı gibi `using` bir yönergeyle `using namespace std;`kapsam içine alınmalıdır, ya da üye adı, gibi bir `using` bildirim `using std::string;`tarafından kapsam içine alınmalıdır. Aksi takdirde, nitelenmemiş ad geçerli kapsamda bildirilmemiş bir tanımlayıcı olarak kabul edilir.

Tanımlayıcı Kullanıcı tanımlı bir tür için etiketse (örneğin, `class` veya `struct`), kullanılmadan önce etiketin türü bildirilmelidir. Örneğin, kodunuzda bir değişken `struct SomeStruct { /*...*/ };` `SomeStruct myStruct;` bildirebilmeniz için bildirimin mevcut olması gerekir.

Tanımlayıcı bir tür diğer adı ise, tür bir `using` bildirim kullanılarak veya `typedef` kullanılmadan önce bildirilmelidir. Örneğin, için `using my_flags = std::ios_base::fmtflags;` `my_flags` birtürdiğeradıolarakkullanmadanönce`std::ios_base::fmtflags`bildirimini yapmanız gerekir.

## <a name="example-misspelled-identifier"></a>Örnek: yanlış yazılmış tanımlayıcı

Bu hata genellikle tanımlayıcı adı yanlış yazıldığında veya tanımlayıcı yanlış büyük ve küçük harfleri kullandığında oluşur. Bildirimdeki adın, kullandığınız adla tam olarak eşleşmesi gerekir.

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

## <a name="example-use-an-unscoped-identifier"></a>Örnek: kapsamlı olmayan bir tanımlayıcı kullanın

Bu hata, tanımlayıcın doğru bir şekilde Kapsamsız olmaması durumunda oluşabilir. Kullanırken C2065 `cout`görürseniz, bu neden olur. C++ Standart kitaplık işlevleri ve işleçleri ad alanı tarafından tam olarak nitelenmemişse veya bir `std` `using` yönergesi kullanarak ad alanını geçerli kapsama getirmemişse, derleyici bunları bulamaz. Bu sorunu onarmak için, tanımlayıcı adlarını tamamen nitelemeniz veya `using` yönergeyle birlikte ad alanını belirtmeniz gerekir.

Bu örnek, `cout` `endl` ad`std` alanında tanımlandığından derlenmesi başarısız olur:

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

`class`,, `struct` Veya`enum class` türleri içinde belirtilen tanımlayıcılar, bu kapsam dışında kullandığınızda, kapsayan kapsam adları tarafından da nitelenmelidir.

## <a name="example-precompiled-header-isnt-first"></a>Örnek: önceden derlenmiş üstbilgi ilk değil

Bu hata, önceden derlenmiş bir üstbilgi dosyasının #include önce #include, #define veya #pragma gibi herhangi bir Önişlemci yönergesi yerleştirirseniz meydana gelebilir. Kaynak dosyanız önceden derlenmiş bir üstbilgi dosyası kullanıyorsa (yani, **/yu** derleyici seçeneği kullanılarak derlenmişse), ön derlenmiş üstbilgi dosyası yok sayılacak önce tüm Önişlemci yönergeleri.

Bu örnek, ön derlenmiş üstbilgi `cout` dosyasından `endl` önce dahil edildiği için \<yoksayılan ve ıostream > üst bilgisinde tanımlandığından derleme işlemi başarısız olur. Bu örneği oluşturmak için, üç dosyayı oluşturun, ardından stbafx. cpp öğesini derleyin ve ardından C2065_pch. cpp derleyin.

```cpp
// pch.h (stdafx.h in Visual Studio 2017 and earlier)
#include <stdio.h>
```

```cpp
// pch.cpp (stdafx.cpp in Visual Studio 2017 and earlier)
// Compile by using: cl /EHsc /W4 /c /Ycstdafx.h stdafx.cpp
#include "pch.h"
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

Bu sorunu onarmak için, \<ıostream > #include ön derlenmiş üstbilgi dosyasına ekleyin veya ön derlenmiş üstbilgi dosyası kaynak dosyanıza dahil edildikten sonra taşıyın.

## <a name="example-missing-header-file"></a>Örnek: başlık dosyası eksik

Tanımlayıcıyı bildiren üst bilgi dosyasını dahil edilmedi. Tanımlayıcının bildirimini içeren dosyanın onu kullanan her kaynak dosyasına eklendiğinden emin olun.

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

\<İnitializer_list > üst bilgisini dahil etmeden bir başlatıcı listesi kullanıyorsanız, bunun olası bir nedeni vardır.

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

, `VC_EXTRALEAN` `WIN32_LEAN_AND_MEAN`Veya tanımlarsanızbuhatayıWindowsMasaüstüuygulamakaynakdosyalarındagörebilirsiniz.`WIN32_EXTRA_LEAN` Bu Önişlemci makroları, derleme hızını hızlandırmak için Windows. h ve afxv\_W32. h içindeki bazı üst bilgi dosyalarını dışarıda bırakır. Dışlananlar için güncel bir açıklama için Windows. h ve afxv_w32. h ' ye bakın.

## <a name="example-missing-closing-quote"></a>Örnek: eksik kapanış tırnağı

Bu hata, bir dize sabitinden sonra bir kapanış tırnağı eksik olduğunda meydana gelebilir. Bu, derleyicisini karıştırmanın kolay bir yoludur. Eksik kapanış teklifinin, bildirilen hata konumundan önce birkaç satır olabileceğini unutmayın.

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

## <a name="example-use-iterator-outside-for-loop-scope"></a>Örnek: döngü kapsamı dışında Yineleyici kullanın

Bu hata, bir `for` döngüye bir yineleyici değişkeni bildirdiğinizde ve sonra bu yineleyici değişkenini `for` döngünün kapsamı dışında kullanmaya çalıştığınızda oluşabilir. Derleyici, [/Zc: forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) derleyici seçeneğini varsayılan olarak sunar. Daha fazla bilgi için bkz. [hata ayıklama Yineleyici desteği](../../standard-library/debug-iterator-support.md) .

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

## <a name="example-preprocessor-removed-declaration"></a>Örnek: Önişlemci kaldırıldı bildirimi

Bu hata, geçerli yapılandırmanız için derlenmemiş koşullu koda Derlenmiş koddaki bir işleve veya değişkene başvurursanız oluşur. Bu, şu anda yapı ortamınızda desteklenmeyen bir başlık dosyasında bir işlevi çağırdığınızda de oluşabilir. Bazı değişkenler veya işlevler yalnızca belirli bir önişlemci makrosu tanımlandığında kullanılabilir ise, bu işlevleri çağıran kodun yalnızca aynı önişlemci makrosu tanımlandığında derlendiğinden emin olun. Bu sorun, gerekli Önişlemci makroları geçerli derleme yapılandırması için tanımlanmamışsa, işlev bildirimi, IDE 'de kolayca belirlenir.

Bu, hata ayıklama sırasında oluşturduğunuz ancak perakende olmayan bir kod örneğidir:

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

## <a name="example-ccli-type-deduction-failure"></a>Örnek: C++/CLı tür kesintisi hatası

Amaçlanan tür bağımsız değişkeni kullanılan parametrelerden çıkarsanmıyorsa, bu hata genel bir işlev çağrılırken meydana gelebilir. Daha fazla bilgi için bkz. [genel işlevlerC++(/CLI)](../../extensions/generic-functions-cpp-cli.md).

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

## <a name="example-ccli-attribute-parameters"></a>Örnek: C++/CLı öznitelik parametreleri

Bu hata, Visual Studio 2005 için yapılan derleyici uygunluk işinin sonucu olarak da oluşturulabilir: görsel C++ öznitelikler için parametre denetimi.

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
