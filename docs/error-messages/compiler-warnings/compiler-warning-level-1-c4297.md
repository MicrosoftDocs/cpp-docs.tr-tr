---
title: Derleyici Uyarısı (düzey 1) C4297
ms.date: 11/04/2016
f1_keywords:
- C4297
helpviewer_keywords:
- C4297
ms.assetid: ba92fcdc-9f70-4f60-abe6-281f9582ca59
ms.openlocfilehash: 31deba2f421b461ba56d13810b5064b353a0e602
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175681"
---
# <a name="compiler-warning-level-1-c4297"></a>Derleyici Uyarısı (düzey 1) C4297

' function ': işlevin özel durum oluşturması, ancak

Bir işlev bildirimi (muhtemelen örtük) `noexcept` Belirleyicisi, boş bir `throw` özel durum belirleyicisi veya bir [__declspec (nothrow)](../../cpp/nothrow-cpp.md) özniteliği içerir ve tanım bir veya daha fazla [throw](../../cpp/try-throw-and-catch-statements-cpp.md) deyimi içerir. C4297 çözümlemek için, `__declspec(nothrow)`, `noexcept(true)` veya `throw()`olarak belirtilen işlevlerde özel durumlar yapmayı denemeyin. Alternatif olarak, `noexcept`, `throw()`veya `__declspec(nothrow)` belirtimini kaldırın.

Varsayılan olarak, derleyici Kullanıcı tanımlı Yıkıcılar ve deayırıcı işlevleri ve derleyicinin ürettiği özel üye işlevleri için örtük `noexcept(true)` belirticileri üretir. Bu, ISO C++ 11 standardına uygundur. Örtük noexcept belirticileri oluşturmayı engellemek ve derleyiciyi Visual Studio 2013 standart olmayan davranışına dönüştürmek için **/Zc: implicitNoexcept-** derleyici seçeneğini kullanın. Daha fazla bilgi için bkz. [/Zc: implicitNoexcept (örtük özel durum tanımlayıcıları)](../../build/reference/zc-implicitnoexcept-implicit-exception-specifiers.md).

Özel durum belirtimleri hakkında daha fazla bilgi için bkz. [özel durum belirtimleri (throw)](../../cpp/exception-specifications-throw-cpp.md). Ayrıca, derleme zamanında özel durum işleme davranışının nasıl değiştirileceği hakkında bilgi için bkz. [/Eh (özel durum Işleme modeli)](../../build/reference/eh-exception-handling-model.md) .

Bu uyarı, C++ işlev olsalar bile extern "C" olarak işaretlenmiş __declspec ([dllexport](../../cpp/dllexport-dllimport.md)) işlevleri için de oluşturulur.

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
