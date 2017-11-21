---
title: "Özel durum belirtimleri (throw) (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- exceptions [C++], exception specifications
- throwing exceptions [C++], throw keyword
- C++ exception handling [C++], throwing exceptions
- throw keyword [C++], throw() vs. throw(...)
- throw keyword [C++], exception specifications
ms.assetid: 4d3276df-6f31-4c7f-8cab-b9d2d003a629
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e308d95f25b25a99fecde976d8ba6433316f460f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="exception-specifications-throw-noexcept-c"></a>Özel durum belirtimleri (throw, noexcept) (C++)
Özel durum belirtimleri Programcı hedefi bir işlev tarafından yayılan özel durum türleri hakkında belirten bir C++ dili özelliğidir. Bir işlev olabilir veya bir özel durum tarafından kullanarak sonlandırılabilir değil belirtebilirsiniz bir *özel durum belirtimi*. Beklenmeyen bir özel durum, programı sonlandırmak için işlevi çıkışları ve derleyici işlev çağrıları iyileştirmek için bu bilgileri kullanabilirsiniz. Özel durum belirtimi iki tür vardır. *Noexcept belirtimi* C ++ 11'de yenidir. Escape işlevi olası özel durumları kümesi boş olup olmadığını belirtir. *Dinamik özel durum belirtimi*, veya `throw(optional_type_list)` belirtimi, C ++ 11'de kullanım dışıdır ve yalnızca kısmen Visual Studio tarafından desteklenir. Bu özel durum belirtimi hangi özel durumlar dışında bir işlev atılabilen hakkında özet bilgileri sağlamak için tasarlanmıştır ancak uygulamada sorunlu olarak bulunamadı. Biraz kullanışlı olması için kanıtlamak bir dinamik özel durum belirtimi koşulsuz edildi `throw()` belirtimi. Örneğin, işlev bildirimi:  
  
```cpp  
void MyFunction(int i) throw();  
```  
  
 Derleyici işlevi tüm özel durumlar oluşturmadığını söyler. Bunu kullanarak eşdeğerdir [__declspec(nothrow)](../cpp/nothrow-cpp.md). Kullanımı isteğe bağlı olarak kabul edilir.  
  
ISO C ++ 11 standart içinde [noexcept](../cpp/noexcept-cpp.md) işleci yerine sunulmuştur. Visual Studio 2015 ve sonraki sürümlerinde desteklenir. Mümkün olduğunda kullanın bir `noexcept` ifadesi bir işlev özel durumlar oluşturma belirtin. Örneğin, bu işlev bildirimi yerine yukarıdaki kullanın:  
  
```cpp  
void MyFunction(int i) noexcept;  
```  
  
Visual C++ tam olarak desteklerken `noexcept` ifadesi, onu departs ISO C++ standart dinamik özel durum belirtimleri uygulamaya.  Aşağıdaki tabloda, özel durum belirtimleri Visual C++ uygulaması özetlenmektedir:  
  
|Özel durum belirtimi|Açıklama|  
|-----------------------------|-------------|  
|`noexcept`<br/>`noexcept(true)`<br/>`throw()`|İşlev bir özel durum değil. Ancak, olarak işaretlenmiş bir işlev dışında bir özel durum, `throw()`, Visual C++ Derleyici çağrıları `std::terminate`değil `std::unexpected`. Bkz: [std::unexpected](../c-runtime-library/reference/unexpected-crt.md) daha fazla bilgi için. Bir işlev işaretlenmişse `noexcept`, `noexcept(true)`, veya `throw()`, Visual C++ derleyicisi varsayar işlevi C++ özel durumlar oluşturmadığını ve kodu buna uygun olarak oluşturur. Kod en iyi duruma getirme, bir işlev bir özel durum, işlevi her C++ özel durumlar oluşturmadığını duymadığını C++ derleyicisi tarafından gerçekleştirilen çünkü programın doğru şekilde yürütülmeyebilir.|  
|`noexcept(false)`<br/>`throw(...)`<br/>Hiçbir belirtimi|İşlev herhangi bir türde bir özel durum.|  
|`throw(type)`|İşlev türünde bir özel durum atabilirsiniz `type`. Visual C++'da, bu söz dizimini kabul edilir, ancak bu olarak yorumlanır `noexcept(false)`.|  
  
 Özel durum işleme uygulamada kullanılırsa, olmalıdır bir işlev işlevi dış kapsamını çıkmadan önce özel durum işleyici işaretlenen çağrı yığınında `noexcept`, `noexcept(true)`, veya `throw()`. Tüm işlevler arasında çağrıldıklarında aykırı tek ve özel durumu işler biri olarak belirtilen `noexcept`, `noexcept(true)`, veya `throw()`, özel durum noexcept işlevi yayar program kesilir.  
  
 Bir işlev özel durum davranışını aşağıdaki etkenlere bağlıdır:  
  
-   Olup C veya C++ altında işlevi derlediğiniz.  
  
-   Hangi [/EH](../build/reference/eh-exception-handling-model.md) derleyici seçeneği kullanın.  
  
-   Olup olmadığını açıkça özel durum belirtimi belirtin.  
  
 Açık özel durum belirtimleri C işlevlerini izin verilmez. C işlev altında özel durumlar oluşturma değil varsayılır **/EHsc**ve yapılandırılmış özel durum altında atabilir **/EHs**, **/EHa**, veya **/EHac**.  
  
 C++ işlevi olası seçenekleri çeşitli derleyici özel durum işleme altında atabilir olup olmadığını aşağıdaki tabloda özetlenmiştir:  
  
|İşlev|/ EHsc|/ EHs|/ EHa|/ EHac|  
|--------------|------------|-----------|-----------|------------|  
|Hiçbir özel durum belirtimiyle C++ işlevi|Evet|Evet|Evet|Evet|  
|C++ işleviyle `noexcept`, `noexcept(true)`, veya `throw()` özel durum belirtimi|Hayır|Hayır|Evet|Evet|  
|C++ işleviyle `noexcept(false)`, `throw(...)`, veya `throw(type)` özel durum belirtimi|Evet|Evet|Evet|Evet|  
  
## <a name="example"></a>Örnek  
  
```cpp  
// exception_specification.cpp  
// compile with: /EHs  
#include <stdio.h>  
  
void handler() {  
   printf_s("in handler\n");  
}  
  
void f1(void) throw(int) {  
   printf_s("About to throw 1\n");  
   if (1)  
      throw 1;  
}  
  
void f5(void) throw() {  
   try {  
      f1();  
   }  
   catch(...) {  
      handler();  
    }  
}  
  
// invalid, doesn't handle the int exception thrown from f1()  
// void f3(void) throw() {  
//   f1();  
// }  
  
void __declspec(nothrow) f2(void) {  
   try {  
      f1();  
   }  
   catch(int) {  
      handler();  
    }  
}  
  
// only valid if compiled without /EHc   
// /EHc means assume extern "C" functions don't throw exceptions  
extern "C" void f4(void);  
void f4(void) {  
   f1();  
}  
  
int main() {  
   f2();  
  
   try {  
      f4();  
   }  
   catch(...) {  
      printf_s("Caught exception from f4\n");  
   }  
   f5();  
}  
```  
  
```Output  
About to throw 1  
in handler  
About to throw 1  
Caught exception from f4  
About to throw 1  
in handler  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [deneyin, throw ve catch deyimleri (C++)](../cpp/try-throw-and-catch-statements-cpp.md)   
 [C++ özel durum işleme](../cpp/cpp-exception-handling.md)