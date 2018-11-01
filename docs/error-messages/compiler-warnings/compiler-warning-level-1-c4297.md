---
title: Derleyici Uyarısı (düzey 1) C4297
ms.date: 11/04/2016
f1_keywords:
- C4297
helpviewer_keywords:
- C4297
ms.assetid: ba92fcdc-9f70-4f60-abe6-281f9582ca59
ms.openlocfilehash: 07dd6c65498ddd0d377ec3e0fbc7b44e52bec96b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50540263"
---
# <a name="compiler-warning-level-1-c4297"></a>Derleyici Uyarısı (düzey 1) C4297

'function': işlev kabul ancak bir özel durum oluşturması beklenmiyor

Bir işlev bildirimi bir (muhtemelen örtük) içeren `noexcept` tanımlayıcısı, boş bir `throw` özel durum tanımlayıcısı veya bir [__declspec(nothrow)](../../cpp/nothrow-cpp.md) özniteliği ve tanımını içeren bir veya daha fazla [throw ](../../cpp/try-throw-and-catch-statements-cpp.md) deyimleri. C4297 çözmek için bildirilen işlevler özel durumlar çalışmayın `__declspec(nothrow)`, `noexcept(true)` veya `throw()`. Alternatif olarak, kaldırma `noexcept`, `throw()`, veya `__declspec(nothrow)` belirtimi.

Varsayılan olarak, derleyici örtük oluşturur `noexcept(true)` kullanıcı tanımlı yıkıcı ve birleştiricinin işlevleri ve derleyicinin ürettiği özel üye işlevleri tanımlayıcıları. Bu, ISO C ++ 11 standardına uyar. Örtük noexcept belirticisi oluşturulmasını önlemek ve Visual Studio 2013'ün standart olmayan davranış derleyiciye dönmek için kullandığınız **/Zc:implicitNoexcept-** derleyici seçeneği. Daha fazla bilgi için [/ZC: implicitnoexcept (örtük özel durum tanımlayıcıları)](../../build/reference/zc-implicitnoexcept-implicit-exception-specifiers.md).

Özel durum belirtimleri hakkında daha fazla bilgi için bkz. [özel durum belirtimleri (throw)](../../cpp/exception-specifications-throw-cpp.md). Ayrıca bkz [/EH (özel durum işleme modeli)](../../build/reference/eh-exception-handling-model.md) özel durum işleme derleme zamanında değişiklik yapma hakkında bilgi için.

Bu uyarı için __declspec da oluşturulur ([dllexport](../../cpp/dllexport-dllimport.md)) işlevleri C++ işlevlerini olsalar bile extern "C" olarak işaretlenmiş.

Aşağıdaki örnek, C4297 oluşturur:

```
// C4297.cpp
// compile with: /W1 /LD
void __declspec(nothrow) f1()   // declared nothrow
// try the following line instead
// void f1()
{
   throw 1;   // C4297
}
```