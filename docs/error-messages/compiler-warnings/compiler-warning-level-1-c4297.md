---
title: Derleyici Uyarısı (düzey 1) C4297
ms.date: 11/04/2016
f1_keywords:
- C4297
helpviewer_keywords:
- C4297
ms.assetid: ba92fcdc-9f70-4f60-abe6-281f9582ca59
ms.openlocfilehash: 53c9a3c311f0136136c1c57438860edcc0766e0f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220073"
---
# <a name="compiler-warning-level-1-c4297"></a>Derleyici Uyarısı (düzey 1) C4297

' function ': işlevin özel durum oluşturması, ancak

İşlev bildiriminde bir (muhtemelen örtük) **`noexcept`** tanımlayıcı, boş bir **`throw`** özel durum belirleyicisi veya [__declspec (nothrow)](../../cpp/nothrow-cpp.md) özniteliği bulunur ve tanım bir veya daha fazla [throw](../../cpp/try-throw-and-catch-statements-cpp.md) deyimi içerir. C4297 çözümlemek için, veya olarak belirtilen işlevlerde özel durumlar yapmayı denemeyin `__declspec(nothrow)` `noexcept(true)` `throw()` . Alternatif olarak,, **`noexcept`** `throw()` veya belirtimini kaldırın `__declspec(nothrow)` .

Varsayılan olarak, derleyici `noexcept(true)` Kullanıcı tanımlı Yıkıcılar ve deayırıcı işlevleri ve derleyicinin ürettiği özel üye işlevleri için örtük tanımlayıcılar oluşturur. Bu, ISO C++ 11 standardına uygundur. Örtük noexcept belirticileri oluşturmayı engellemek ve derleyiciyi Visual Studio 2013 standart olmayan davranışına dönüştürmek için **/Zc: implicitNoexcept-** derleyici seçeneğini kullanın. Daha fazla bilgi için bkz. [/Zc: implicitNoexcept (örtük özel durum tanımlayıcıları)](../../build/reference/zc-implicitnoexcept-implicit-exception-specifiers.md).

Özel durum belirtimleri hakkında daha fazla bilgi için bkz. [özel durum belirtimleri (throw)](../../cpp/exception-specifications-throw-cpp.md). Ayrıca, derleme zamanında özel durum işleme davranışının nasıl değiştirileceği hakkında bilgi için bkz. [/Eh (özel durum Işleme modeli)](../../build/reference/eh-exception-handling-model.md) .

Bu uyarı, C++ işlevleri olsalar bile extern "C" olarak işaretlenmiş __declspec ([dllexport](../../cpp/dllexport-dllimport.md)) işlevleri için de oluşturulur.

Aşağıdaki örnek C4297 oluşturur:

```cpp
// C4297.cpp
// compile with: /W1 /LD
void __declspec(nothrow) f1()   // declared nothrow
// try the following line instead
// void f1()
{
   throw 1;   // C4297
}
```
