---
title: Özel durum belirtimleri (throw, noexcept) (C++) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2018
ms.technology:
- cpp-language
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
ms.workload:
- cplusplus
ms.openlocfilehash: 15e872faab5beee296e4543c8404141428345842
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402409"
---
# <a name="exception-specifications-throw-noexcept-c"></a>Özel durum belirtimleri (throw, noexcept) (C++)

Özel durum belirtimleri, işlev tarafından yayılan özel durum türleri hakkında programcının amacını belirten bir C++ dil özelliğidir. Bir işlevi olabilir veya bir özel durumun kullanarak sonlandırılabilir değil belirtebileceğiniz bir *özel durum belirtimi*. İşlev beklenmeyen bir özel durum, program sona erdirmek için çıkışları ve derleyici işlev için çağrılar iyileştirmek için bu bilgileri kullanabilirsiniz. 

C ++ 17 önce özel durum belirtimi iki çeşit vardı. *Noexcept belirtimi* C ++ 11'de yeni olan. Bu işlev kaçış yapılacağını da olası özel durumları kümesi boş olup olmadığını belirtir. *Dinamik özel durum belirtimi*, veya `throw(optional_type_list)` belirtimi, C ++ 11'de kullanım dışı ve C ++ 17'de hariç kaldırıldı `throw()`, için bir diğer ad olduğu `noexcept(true)`. Bu özel durum belirtimi, bir işlevin hangi özel durumları muhtemel hakkında özet bilgi sağlamak için tasarlanmıştır ancak uygulamada sorunlu bulunamadı. Biraz faydalı olarak kanıtlamak bir dinamik özel durum belirtimi koşulsuz olan `throw()` belirtimi. Örneğin, işlev bildirimi:

```cpp
void MyFunction(int i) throw();
```
derleyiciye işlevin özel durum oluşturmadığını söyler. Bununla birlikte, **/Std: c ++ 14** modu için açabilir bunu tanımsız davranış, işlev bir özel durum oluşturmaz. Bu nedenle kullanılmasını öneririz [noexcept](../cpp/noexcept-cpp.md) yerine yukarıdaki işleci:

```cpp
void MyFunction(int i) noexcept;
```
Özel durum belirtimleri Microsoft Visual C++ uygulaması aşağıdaki tabloda özetlenmiştir:

|Özel durum belirtimi|Açıklama|
|-----------------------------|-------------|
|`noexcept`<br>`noexcept(true)`<br>`throw()`|İşlev bir özel durum oluşturmaz. İçinde [/Std: c ++ 14](../build/reference/std-specify-language-standard-version.md) (varsayılandır) modunu `noexcept` ve `noexcept(true)` eşdeğerdir. Bir özel durum bildirildi bir işlevden harekete geçirildiğinde `noexcept` veya `noexcept(true)`, [std::terminate](../standard-library/exception-functions.md#terminate) çağrılır. Olarak bildirilen bir işlevden bir özel durum harekete geçirildiğinde `throw()` içinde **/Std: c ++ 14** modu, sonucun tanımsız davranış olduğu. Belirli bir işlevi çağrılır. Bu, derleyicinin çağırmak için gereken bir Geçitler C ++ 14 standardı'ndan [std::unexpected](../standard-library/exception-functions.md#unexpected).  <br> **Visual Studio 2017 sürüm 15.5 ve üzeri**: içinde **/Std: c ++ 17** modu `noexcept`, `noexcept(true)`, ve `throw()` tüm eşdeğerdir. İçinde **/Std: c ++ 17** modu `throw()` için bir diğer addır `noexcept(true)`. İçinde **/Std: c ++ 17** modu, tüm bu özellikleri ile bildirilen bir işlevden bir özel durum oluştuğunda [std::terminate](../standard-library/exception-functions.md#terminate) çağrılır C ++ 17 standart tarafından gerekli.|
|`noexcept(false)`<br/>`throw(...)`<br/>Belirtim|İşlev herhangi bir türde bir durum oluşturabilir.|
|`throw(type)`| (**c ++ 14 ve önceki**) işlev türünde bir özel durum oluşturabilecek `type`. Derleyici söz dizimini kabul eder, ancak bunu olarak yorumlar `noexcept(false)`. İçinde **/Std: c ++ 17** modu derleyici C5040 uyarı verir.|

Özel durum işleme bir uygulamada kullanılırsa, olmalıdır bir işlev, dış kapsamdaki işlev çıkmadan önce özel durumlar tanıtıcıları işaretlenen çağrı yığınında `noexcept`, `noexcept(true)`, veya `throw()`. Arasında herhangi bir işlev çağrılırsa, bir özel durum oluşturur, diğeri özel durumu işleyen olarak belirtilen `noexcept`, `noexcept(true)` (veya `throw()` içinde **/Std: c ++ 17** modu), programın ne zaman sonlandırılır. noexcept işlevi, özel durum yayar.

Bir işlevin özel durum davranışını aşağıdaki etkenlere bağlıdır:

- Hangi [dil standart derleme modu](../build/reference/std-specify-language-standard-version.md) ayarlanır.
- C veya C++ işlevi mi derlediğiniz.

- Hangi [/EH](../build/reference/eh-exception-handling-model.md) derleyici seçeneğini kullandığınız.

- Olup açık özel durum belirtimi belirtin.

Açık belirtimlere C işlevlerinde izin verilmez. C işlev altında özel durum oluşturması beklenmiyor varsayılır **/ehsc**ve altında yapılandırılmış özel durum oluşturabildiğini varsaymasını **EHS**, **/eha**, veya **/EHac**.

Bir C++ işlev olası seçenekleri çeşitli derleyici özel durum işleme altında atabilir olup olmadığını, aşağıdaki tabloda özetlenmiştir:

|İşlev|/ EHsc|/ EHs|/ EHa|/EHac|
|--------------|------------|-----------|-----------|------------|
|Özel durum belirtimi olmadan C++ işlevi|Evet|Evet|Evet|Evet|
|İle C++ işlevi `noexcept`, `noexcept(true)`, veya `throw()` özel durum belirtimi|Hayır|Hayır|Evet|Evet|
|İle C++ işlevi `noexcept(false)`, `throw(...)`, veya `throw(type)` özel durum belirtimi|Evet|Evet|Evet|Evet|

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

## <a name="see-also"></a>Ayrıca bkz.
 [try, throw ve catch Deyimleri (C++)](../cpp/try-throw-and-catch-statements-cpp.md)  
 [C++ Özel Durum İşleme](../cpp/cpp-exception-handling.md)