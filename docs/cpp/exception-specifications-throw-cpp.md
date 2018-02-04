---
title: "Özel durum belirtimleri (throw, noexcept) (C++) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- exceptions [C++], exception specifications
- throwing exceptions [C++], throw keyword
- C++ exception handling [C++], throwing exceptions
- throw keyword [C++]
- noexcept keyword [C++]
ms.assetid: 4d3276df-6f31-4c7f-8cab-b9d2d003a629
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cbd45c8afed11f613722ecc7586436ff707042d7
ms.sourcegitcommit: 30ab99c775d99371ed22d1a46598e542012ed8c6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2018
---
# <a name="exception-specifications-throw-noexcept-c"></a>Özel durum belirtimleri (throw, noexcept) (C++)

Özel durum belirtimleri Programcı hedefi bir işlev tarafından yayılan özel durum türleri hakkında belirten bir C++ dili özelliğidir. Bir işlev olabilir veya bir özel durum tarafından kullanarak sonlandırılabilir değil belirtebilirsiniz bir *özel durum belirtimi*. Beklenmeyen bir özel durum, programı sonlandırmak için işlevi çıkışları ve derleyici işlev çağrıları iyileştirmek için bu bilgileri kullanabilirsiniz. 

C ++ 17 önce özel durum belirtimi iki tür vardı. *Noexcept belirtimi* C ++ 11'de yeni oluştu. Escape işlevi olası özel durumları kümesi boş olup olmadığını belirtir. *Dinamik özel durum belirtimi*, veya `throw(optional_type_list)` belirtimi, C ++ 11'de kullanım dışı ve dışında C ++ 17'de kaldırılan `throw()`, için diğer ad olduğu `noexcept(true)`. Bu özel durum belirtimi hangi özel durumlar dışında bir işlev atılabilen hakkında özet bilgileri sağlamak için tasarlanmıştır ancak uygulamada sorunlu olarak bulunamadı. Biraz kullanışlı olması için kanıtlamak bir dinamik özel durum belirtimi koşulsuz edildi `throw()` belirtimi. Örneğin, işlev bildirimi:

```cpp
void MyFunction(int i) throw();
```
Derleyici işlevi tüm özel durumlar oluşturmadığını söyler. Bununla birlikte, **/Std: c ++ 14** modu için açabilir bu işlev bir özel durum, davranış tanımlanmamış. Bu nedenle kullanmanızı öneririz [noexcept](../cpp/noexcept-cpp.md) yerine bir yukarıdaki işleci:

```cpp
void MyFunction(int i) noexcept;
```
Aşağıdaki tabloda, özel durum belirtimleri Microsoft Visual C++ uygulaması özetlenmektedir:

|Özel durum belirtimi|Açıklama|
|-----------------------------|-------------|
|`noexcept`<br>`noexcept(true)`<br>`throw()`|İşlev bir özel durum değil. İçinde [/Std: c ++ 14](../build/reference/std-specify-language-standard-version.md) (varsayılan değer olan) mod `noexcept` ve `noexcept(true)` eşdeğerdir. Ne zaman özel durum bildirilmiş bir işlevden `noexcept` veya `noexcept(true)`, [std::terminate](../standard-library/exception-functions.md#terminate) çağrılır. Bir özel bir işleve zaman durum olarak bildirilen `throw()` içinde **/Std: c ++ 14** , sonuç modudur tanımsız davranış. Belirli bir işlev çağrılır. Derleyicinin çağırmak için gereken bir Geçitler C ++ 14 standart, gelen budur [std::unexpected](../standard-library/exception-functions.md#unexpected).  <br> **Visual Studio 2017 15,5 ve sonraki sürümleri**: içinde **/Std: c ++ 17** modu, `noexcept`, `noexcept(true)`, ve `throw()` tüm eşdeğerdir. İçinde **/Std: c ++ 17** modu, `throw()` için diğer ad olduğu `noexcept(true)`. İçinde **/Std: c ++ 17** herhangi bu belirtimlere bildirilen bir işlevden bir özel durum oluştuğunda modu [std::terminate](../standard-library/exception-functions.md#terminate) çağrılır C ++ 17 standart gerektirdiği.|
|`noexcept(false)`<br/>`throw(...)`<br/>Hiçbir belirtimi|İşlev herhangi bir türde bir özel durum.|
|`throw(type)`| (**c ++ 14 ve daha önceki**) işlevi türünde bir özel durum atabilirsiniz `type`. Derleyici söz dizimini kabul eder, ancak bunu olarak yorumlar `noexcept(false)`. İçinde **/Std: c ++ 17** modu derleyici C5040 uyarı verir.|

Özel durum işleme uygulamada kullanılırsa, olmalıdır bir işlev işlevi dış kapsamını çıkmadan önce özel durum işleyici işaretlenen çağrı yığınında `noexcept`, `noexcept(true)`, veya `throw()`. Tüm işlevler arasında çağrıldıklarında aykırı tek ve özel durumu işler biri olarak belirtilen `noexcept`, `noexcept(true)` (veya `throw()` içinde **/Std: c ++ 17** modu), programın ne zaman sonlandırıldı özel durum noexcept işlevi yayar.

Bir işlev özel durum davranışını aşağıdaki etkenlere bağlıdır:

- Hangi [dil standart bir derleme moduna](../build/reference/std-specify-language-standard-version.md) ayarlanır.
- Olup C veya C++ altında işlevi derlediğiniz.

- Hangi [/EH](../build/reference/eh-exception-handling-model.md) derleyici seçeneği kullanın.

- Olup olmadığını açıkça özel durum belirtimi belirtin.

Açık özel durum belirtimleri C işlevlerini izin verilmez. C işlev altında özel durumlar oluşturma değil varsayılır **/EHsc**ve yapılandırılmış özel durum altında atabilir **/EHs**, **/EHa**, veya **/EHac**.

C++ işlevi olası seçenekleri çeşitli derleyici özel durum işleme altında atabilir olup olmadığını aşağıdaki tabloda özetlenmiştir:

|İşlev|/EHsc|/EHs|/EHa|/EHac|
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

 [deneyin, throw ve catch deyimleri (C++)](../cpp/try-throw-and-catch-statements-cpp.md) [C++ özel durum işleme](../cpp/cpp-exception-handling.md)