---
description: 'Daha fazla bilgi edinin: özel durum belirtimleri (throw, noexcept) (C++)'
title: Özel durum belirtimleri (throw, noexcept) (C++)
ms.date: 01/18/2018
helpviewer_keywords:
- exceptions [C++], exception specifications
- throwing exceptions [C++], throw keyword
- C++ exception handling [C++], throwing exceptions
- throw keyword [C++]
- noexcept keyword [C++]
ms.assetid: 4d3276df-6f31-4c7f-8cab-b9d2d003a629
ms.openlocfilehash: a6b3cb808caf464dc3dd19ea4d34e9d68f09d0d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164814"
---
# <a name="exception-specifications-throw-noexcept-c"></a>Özel durum belirtimleri (throw, noexcept) (C++)

Özel durum belirtimleri, programcı 'nin bir işlev tarafından yayabileceği özel durum türleri hakkında amacını gösteren bir C++ dili özelliğidir. Bir işlevin özel durum *belirtimi* kullanarak bir özel durumla ilgili veya çıkış yapabilir olduğunu belirtebilirsiniz. Derleyici, bu bilgileri işleve yapılan çağrıları iyileştirmek ve beklenmeyen bir özel durum işlevi iptal ederseniz programı sonlandırmak için kullanabilir.

C++ 17 ' den önce iki tür özel durum belirtimi vardı. *Noexcept belirtimi* , c++ 11 ' de yenidir. Bu, işlevi kaçırabilecek olası özel durumların kümesinin boş olup olmadığını belirtir. *Dinamik özel durum belirtimi* veya `throw(optional_type_list)` belirtimi, c++ 11 ' de kullanımdan kaldırılmıştır ve, için `throw()` bir diğer ad olan hariç c++ 17 ' de kaldırılmıştır `noexcept(true)` . Bu özel durum belirtimi, bir işlevden hangi özel durumların atılamayacağını, ancak uygulamada sorunlu olduğunu tespit etmek üzere tasarlanmıştır. Biraz faydalı olması kanıtladığı tek bir dinamik özel durum belirtimi koşulsuz `throw()` belirtimiydi. Örneğin, işlev bildirimi:

```cpp
void MyFunction(int i) throw();
```

derleyiciye işlevin hiçbir özel durum oluşturmadığını söyler. Ancak, **/std: c++ 14** modunda, işlev bir özel durum oluşturması durumunda tanımsız davranışlara neden olabilir. Bu nedenle, yukarıdaki bir yerine [noexcept](../cpp/noexcept-cpp.md) işlecini kullanmanızı öneririz:

```cpp
void MyFunction(int i) noexcept;
```

Aşağıdaki tabloda özel durum belirtimlerinin Microsoft C++ uygulamasını özetlenmektedir:

|Özel durum belirtimi|Anlamı|
|-----------------------------|-------------|
|**`noexcept`**<br/>`noexcept(true)`<br/>`throw()`|İşlev bir özel durum oluşturmaz. [/Std: c++ 14](../build/reference/std-specify-language-standard-version.md) modunda (varsayılan olarak) **`noexcept`** ve `noexcept(true)` eşdeğerdir. Veya olarak belirtilen bir işlevden özel durum oluştuğunda **`noexcept`** `noexcept(true)` , [std:: Terminate](../standard-library/exception-functions.md#terminate) çağrılır. `throw()` **/Std: c++ 14** modunda olarak belirtilen bir işlevden özel durum oluştuğunda, sonuç tanımsız bir davranıştır. Belirli bir işlev çağrılmaz. Bu, C++ 14 standbundan ayrılan ve derleyicinin [std:: beklenmeyen](../standard-library/exception-functions.md#unexpected)bir şekilde çağrılmasını gerektiren bir farklılaşma anlamına gelir.  <br/> **Visual Studio 2017 sürüm 15,5 ve üzeri**: **/std: c++ 17** modunda,, **`noexcept`** `noexcept(true)` ve `throw()` hepsi eşdeğerdir. **/Std: c++ 17** modunda, `throw()` için bir diğer addır `noexcept(true)` . **/Std: c++ 17** modunda, bu belirtimlerden biriyle belirtilen bir işlevden bir özel durum oluştuğunda, [std:: Terminate](../standard-library/exception-functions.md#terminate) c++ 17 standardı tarafından gerekli olduğu gibi çağrılır.|
|`noexcept(false)`<br/>`throw(...)`<br/>Belirtim yok|İşlev herhangi türde bir özel durum oluşturabilir.|
|`throw(type)`| (**C++ 14 ve önceki sürümler**) İşlevi türünde bir özel durum oluşturabilir `type` . Derleyici söz dizimini kabul eder, ancak olarak yorumlar `noexcept(false)` . **/Std: c++ 17** modunda derleyici sorunları uyarı C5040.|

Bir uygulamada özel durum işleme kullanılıyorsa, çağrı yığınında, veya olarak işaretlenen bir işlevin dış kapsamından çıkmadan önce, oluşturulan özel durumları işleyen bir işlev olmalıdır **`noexcept`** `noexcept(true)` `throw()` . Bir özel durum oluşturan ve özel durumu işleyen bir işlev arasında çağrılan işlevler **`noexcept`** , `noexcept(true)` (veya `throw()` **/std: c++ 17** modunda) olarak belirtilmişse, noexcept işlevi özel durumu yaydıktan sonra program sonlandırılır.

Bir işlevin özel durum davranışı aşağıdaki etkenlere bağlıdır:

- Hangi [dil standart derleme modu](../build/reference/std-specify-language-standard-version.md) ayarlanır.
- İşlevi C veya C++ altında derlediğiniz olsun.

- Kullandığınız [/Eh](../build/reference/eh-exception-handling-model.md) derleyici seçeneği.

- Özel durum belirtimini açıkça belirtip belirtmeyeceğinizi belirtir.

C işlevlerinde açık özel durum belirtimlerine izin verilmez. Bir C işlevi, **/EHsc** altında özel durum oluşturmayan kabul edilir ve **/EHS**, **/EHa** veya **/EHac** altında yapılandırılmış özel durumlar oluşturabilir.

Aşağıdaki tabloda, bir C++ işlevinin çeşitli derleyici özel durum işleme seçenekleri altında oluşturulup oluşturamayacağını özetlenmektedir:

|İşlev|/EHsc|/EHs|/EHa|/EHac|
|--------------|------------|-----------|-----------|------------|
|Özel durum belirtimi olmayan C++ işlevi|Evet|Evet|Evet|Evet|
|**`noexcept`**, `noexcept(true)` Veya `throw()` özel durum belirtimi ile C++ işlevi|Hayır|Hayır|Evet|Evet|
|`noexcept(false)`, `throw(...)` Veya `throw(type)` özel durum belirtimi ile C++ işlevi|Evet|Evet|Evet|Evet|

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

[try, throw ve catch Deyimleri (C++)](../cpp/try-throw-and-catch-statements-cpp.md)<br/>
[Özel durumlar ve hata işleme için modern C++ en iyi uygulamaları](errors-and-exception-handling-modern-cpp.md)
