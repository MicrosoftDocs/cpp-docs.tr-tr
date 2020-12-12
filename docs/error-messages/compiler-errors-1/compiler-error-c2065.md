---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2065'
title: Derleyici hatası C2065
ms.date: 08/19/2019
f1_keywords:
- C2065
helpviewer_keywords:
- C2065
ms.assetid: 78093376-acb7-45f5-9323-5ed7e0aab1dc
ms.openlocfilehash: a686276aa093e1f2011212d5999d43c76062487f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328552"
---
# <a name="compiler-error-c2065"></a>Derleyici hatası C2065

> '*tanımlayıcı*': bildirilmemiş tanımlayıcı

Derleyici bir tanımlayıcı için bildirimi bulamıyor. Bu hatanın birçok olası nedeni vardır. C2065 'in en yaygın nedenleri, tanımlayıcının bildirilmediği, tanımlayıcının yanlış yazılabileceği, tanımlayıcının bildirildiği üst bilginin dosyada bulunmadığı veya tanımlayıcıda bir kapsam niteleyicisi eksik olduğu, örneğin `cout` yerine `std::cout` . C++ ' daki bildirimler hakkında daha fazla bilgi için bkz. [Bildirimler ve tanımlar (C++)](../../cpp/declarations-and-definitions-cpp.md).

Daha ayrıntılı olarak bazı yaygın sorunlar ve çözümler aşağıda verilmiştir.

## <a name="the-identifier-is-undeclared"></a>Tanımlayıcı bildirilmemiş

Tanımlayıcı bir değişken veya işlev adı ise, kullanılmadan önce bunu bildirmeniz gerekir. İşlev bildirimi, işlev kullanılmadan önce parametrelerinin türlerini de içermelidir. Değişken kullanılarak bildirilirse **`auto`** , derleyicinin türü başlatıcıdan çıkarsanbiliyor olması gerekir.

Tanımlayıcı bir sınıfın veya yapının üyesiyse veya bir ad alanında bildirilirse, yapı, sınıf veya ad alanı kapsamı dışında kullanıldığında sınıf veya yapı adı ya da ad alanı adı tarafından nitelenmelidir. Alternatif olarak, ad alanı gibi bir yönergeyle kapsam içine alınmalıdır **`using`** `using namespace std;` , ya da üye adı, gibi bir bildirim tarafından kapsam içine alınmalıdır **`using`** `using std::string;` . Aksi takdirde, nitelenmemiş ad geçerli kapsamda bildirilmemiş bir tanımlayıcı olarak kabul edilir.

Tanımlayıcı Kullanıcı tanımlı bir tür için etiketse (örneğin, veya), **`class`** **`struct`** kullanılmadan önce etiketin türü bildirilmelidir. Örneğin, `struct SomeStruct { /*...*/ };` kodunuzda bir değişken bildirebilmeniz için bildirimin mevcut olması gerekir `SomeStruct myStruct;` .

Tanımlayıcı bir tür diğer adı ise, tür bir **`using`** bildirim kullanılarak veya **`typedef`** kullanılmadan önce bildirilmelidir. Örneğin, `using my_flags = std::ios_base::fmtflags;` `my_flags` için bir tür diğer adı olarak kullanmadan önce bildirimini yapmanız gerekir `std::ios_base::fmtflags` .

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

Bu hata, tanımlayıcın doğru bir şekilde Kapsamsız olmaması durumunda oluşabilir. Kullanırken C2065 görürseniz `cout` , bu neden olur. C++ standart kitaplığı işlevleri ve işleçleri ad alanı tarafından tam olarak nitelenmemişse veya `std` bir yönergesi kullanarak ad alanını geçerli kapsama getirmemişse **`using`** , derleyici bunları bulamaz. Bu sorunu onarmak için, tanımlayıcı adlarını tamamen nitelemeniz veya yönergeyle birlikte ad alanını belirtmeniz gerekir **`using`** .

Bu örnek `cout` `endl` , ad alanında tanımlandığından derlenmesi başarısız olur `std` :

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

**`class`**,, Veya türleri içinde belirtilen tanımlayıcılar, **`struct`** **`enum class`** Bu kapsam dışında kullandığınızda, kapsayan kapsam adları tarafından da nitelenmelidir.

## <a name="example-precompiled-header-isnt-first"></a>Örnek: önceden derlenmiş üstbilgi ilk değil

Bu hata, önceden derlenmiş bir üstbilgi dosyasının #include önce #include, #define veya #pragma gibi herhangi bir Önişlemci yönergesi yerleştirirseniz meydana gelebilir. Kaynak dosyanız önceden derlenmiş bir üstbilgi dosyası kullanıyorsa (yani, **/yu** derleyici seçeneği kullanılarak derlenmişse), ön derlenmiş üstbilgi dosyası yok sayılacak önce tüm Önişlemci yönergeleri.

Bu örnek `cout` `endl` \<iostream> , ön derlenmiş üstbilgi dosyasından önce dahil edildiği için, üst bilgisinde tanımlandığından derleme için başarısız olur. Bu örneği oluşturmak için, üç dosyayı oluşturun, ardından stbafx. cpp öğesini derleyin ve ardından C2065_pch. cpp derleyin.

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

Bu sorunu onarmak için, ' ın #include \<iostream> ön derlenmiş üstbilgi dosyasına ekleyin veya kaynak dosyanıza ön derlenmiş üstbilgi dosyası eklendikten sonra taşıyın.

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

Bunun nedeni, üstbilgiyi dahil etmeden bir başlatıcı listesi kullanmanız olabilir \<initializer_list> .

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

, Veya tanımlarsanız bu hatayı Windows Masaüstü uygulama kaynak dosyalarında görebilirsiniz `VC_EXTRALEAN` `WIN32_LEAN_AND_MEAN` `WIN32_EXTRA_LEAN` . Bu Önişlemci makroları, derleme hızını hızlandırmak için Windows. h ve afxv W32. h içindeki bazı üst bilgi dosyalarını dışarıda bırakır \_ . Dışlananlar için güncel bir açıklama için Windows. h ve afxv_w32. h ' ye bakın.

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

Bu hata, bir döngüye bir yineleyici değişkeni bildirdiğinizde **`for`** ve sonra bu yineleyici değişkenini döngünün kapsamı dışında kullanmaya çalıştığınızda oluşabilir **`for`** . Derleyici, [/Zc: forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) derleyici seçeneğini varsayılan olarak sunar. Daha fazla bilgi için bkz. [hata ayıklama Yineleyici desteği](../../standard-library/debug-iterator-support.md) .

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

Amaçlanan tür bağımsız değişkeni kullanılan parametrelerden çıkarsanmıyorsa, bu hata genel bir işlev çağrılırken meydana gelebilir. Daha fazla bilgi için bkz. [genel işlevler (C++/CLI)](../../extensions/generic-functions-cpp-cli.md).

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

Bu hata, Visual Studio 2005 için yapılan derleyici uygunluk işinin sonucu olarak da oluşturulabilir: Visual C++ öznitelikleri için parametre denetimi.

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
