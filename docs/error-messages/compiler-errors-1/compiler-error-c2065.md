---
title: "Derleyici Hatası C2065 | Microsoft Docs"
ms.custom: 
ms.date: 09/01/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2065
dev_langs: C++
helpviewer_keywords: C2065
ms.assetid: 78093376-acb7-45f5-9323-5ed7e0aab1dc
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5dec660bd2f47cb1e95569ced6bead2dd42fc2da
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2065"></a>Derleyici Hatası C2065

> '*tanımlayıcısı*': bildirilmemiş tanımlayıcısı  
  
Derleme bildirimi tanımlayıcı için bulunamıyor. Bu hatanın birçok olası nedenleri vardır. C2065 en yaygın nedenlerini tanımlayıcı bildirilmeyen, tanımlayıcı yanlış yazılmış, tanımlayıcı bildirilen burada üstbilgi dosyasına dahil edilmeyen veya tanımlayıcı bir kapsam niteleyicisinde Örneğin, eksik olduğunu olan `cout` yerine `std::cout`. C++'ta bildirimleri hakkında daha fazla bilgi için bkz: [bildirimler ve tanımlar (C++)](../../cpp/declarations-and-definitions-cpp.md).
  
Daha ayrıntılı olarak bazı yaygın sorunlar ve çözümleri şunlardır.

## <a name="the-identifier-is-undeclared"></a>Bildirilmemiş bir tanımlayıcıdır

Tanımlayıcı bir değişken veya işlev adı ise, kullanılmadan önce bildirmelidir. İşlev kullanılabilmesi için önce bir işlev bildirimi parametrelerini türlerini de dahil etmelisiniz. Değişkeni kullanarak bildirilirse `auto`, derleyici, başlatıcı türünden Infer kurabilmesi gerekir.

Tanımlayıcı sınıfta veya yapı üyesi veya bir ad alanında bildirilen varsa, bu sınıfta veya yapı adı veya ad alanı adı yapısı, sınıf veya ad alanı kapsamı dışında kullanıldığında nitelenmiş olmalıdır. Alternatif olarak, ad kapsam içine duruma getirilmesi gereken bir `using` gibi yönerge `using namespace std;`, veya üye adı kapsam içine sunulmalıdır bir `using` bildirimi gibi `using std::string;`. Aksi takdirde, nitelenmemiş adı, geçerli kapsamdaki bildirilmemiş bir tanımlayıcı olarak kabul edilir.

Tanımlayıcı etiketi kullanıcı tanımlı bir tür için örneğin, ise bir `class` veya `struct`, etiket türünü kullanılabilmesi için bildirilmesi gerekir. Örneğin, bildirimi `struct SomeStruct { /*...*/ };` bir değişken bildirebilir önce bulunmalıdır `SomeStruct myStruct;` kodunuzda.

Tanımlayıcı türü diğer adı, türü kullanılarak bildirilmelidir bir `using` bildirimi veya `typedef` kullanılabilmesi için önce. Örneğin, bildirmelisiniz `using my_flags = std::ios_base::fmtflags;` kullanabilmeniz için önce `my_flags` için türü diğer ad olarak `std::ios_base::fmtflags`.
  
## <a name="example-misspelled-identifier"></a>Örnek: yanlış yazılmış tanımlayıcısı  
  
Bu hata genellikle tanımlayıcı adı yanlış yazıldığında veya yanlış büyük ve küçük harfler tanımlayıcısını kullanır oluşur. Ad bildiriminde kullandığınız adı tam olarak eşleşmelidir.  
  
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
  
## <a name="example-use-an-unscoped-identifier"></a>Örnek: dizininden kapsam dışı bir tanımlayıcı kullanın 
  
Bu hata, tanımlayıcı değil düzgün kapsamlıdır oluşabilir. Kullandığınızda C2065 görürseniz `cout`, nedeni budur. Ne zaman C++ Standart Kitaplığı işlevleri ve işleçleri değil tam olarak nitelenmiş ad alanlarına göre veya değil getirdiğiniz `std` kullanarak geçerli kapsam içine ad alanı bir `using` yönergesi derleyici bunları bulunamıyor. Bu sorunu gidermek için tam tanımlayıcı adları nitelemeniz, veya ad alanı belirtin `using` yönergesi.  
  
Bu örnek derlenemiyor çünkü `cout` ve `endl` tanımlanan `std` ad alanı:  
  
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
  
İçinde bildirilen tanımlayıcıları `class`, `struct`, veya `enum class` türleri gerekir ayrıca tam kapsayan kapsamlarına adına göre bu kapsamı dışında kullandığınızda.
  
## <a name="example-missing-header-file"></a>Örnek: üst bilgi dosyası eksik  
  
Tanımlayıcı bildirir üst bilgi dosyasını dahil değildir. Tanımlayıcı bildirimi içeren dosyayı kullanan her kaynak dosyasına bulunduğundan emin olun.  
  
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

Başka bir olası neden, başlatıcı listesi dahil etmeden kullanılmasıdır \<initializer_list > Üstbilgi.

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
  
Tanımlarsanız Windows Masaüstü uygulama kaynak dosyalarında bu hatayı görebilirsiniz `VC_EXTRALEAN`, `WIN32_LEAN_AND_MEAN`, veya `WIN32_EXTRA_LEAN`. Bu Önişlemci makroları windows.h ve afxv bazı başlık dosyalarını dışarıda\_hızlandırmak için w32.h derler. Windows.h ve güncel bir ne dışlandı açıklaması için afxv_w32.h bakın.  
  
## <a name="example-missing-closing-quote"></a>Örnek: kapatma tırnağı eksik  
  
Bu hata, bir dize sabitine sonra kapama çift tırnağı eksik ortaya çıkabilir. Derleyici karmaşık hale getirmeye kolay bir yoludur. Bildirilen hata konumu önce birkaç satırda eksik kapanış tırnak işareti olabileceğine dikkat edin. 
  
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
  
## <a name="example-use-iterator-outside-for-loop-scope"></a>Örnek: dışında yineleyici döngü kapsamında için kullanın.  
  
Bir yineleyici değişken bildirirseniz bu hata oluşabilir bir `for` döngü ve daha sonra deneyin yineleyici değişken kapsamı dışında kullanmak `for` döngü. Derleyicisi tanır [/ZC: forscope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) derleyici seçeneği varsayılan olarak. Bkz: [hata ayıklama yineleyici desteği](../../standard-library/debug-iterator-support.md) daha fazla bilgi için.  
  
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
  
Bir işlev veya geçerli yapılandırmanızı derlenmemiş koşullu derlenmiş kod olduğundan değişken başvurursanız bu hata oluşabilir. Yapı ortamınızda şu anda desteklenmeyen bir üstbilgi dosyasında bir işlevi çağırmak da oluşabilir. Belirli bir önişlemci makrosu tanımlandığında belirli değişkenleri veya işlevler yalnızca varsa, bu işlevler çağıran kodu yalnızca aynı önişlemci makrosu tanımlandığında derlenebilir emin olun. Gerekli Önişlemci makroları geçerli derleme yapılandırmasını tanımlanmazsa bildirimi işlev için devre dışı olduğundan bu IDE içinde nokta için kolay bir sorundur.  
  
Bu, hata ayıklama modunda oluşturmak, ancak değil perakende çalışan bir kod örneğidir:  
  
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
  
## <a name="example-ccli-type-deduction-failure"></a>Örnek: C + +/ CLI tür kesintisi hatası  
  
İstenen tür bağımsız değişkeni kullanılan parametreler anlaşılamıyor bu hata, genel bir işlev çağrılırken ortaya çıkabilir. Daha fazla bilgi için bkz: [genel işlevler (C + +/ CLI)](../../windows/generic-functions-cpp-cli.md).  
  
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
  
## <a name="example-ccli-attribute-parameters"></a>Örnek: C + +/ CLI özniteliği parametreleri  
  
Bu hata için Visual C++ 2005 yapıldığı derleyici uyumluluğu iş sonucunda da oluşturulabilir: Visual C++ öznitelikleri için denetimi parametresi.  
  
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
