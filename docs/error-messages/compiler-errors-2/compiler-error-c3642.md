---
title: Derleyici Hatası C3642
ms.date: 11/04/2016
f1_keywords:
- C3642
helpviewer_keywords:
- C3642
ms.assetid: 429790c2-9614-4d85-b31c-687c8d8f83ff
ms.openlocfilehash: d524c49075c400caa345dd26ed681734ea0cfb94
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582659"
---
# <a name="compiler-error-c3642"></a>Derleyici Hatası C3642

' Döndür_tür/args': bir işlev çağırma kuralı yerel kod içinden __clrcall ile çağrılamaz

İle işaretlenmiş bir işlev [__clrcall](../../cpp/clrcall.md) çağırma kuralı (yönetilmeyen) yerel kod içinden çağrılamaz.

*Döndür_tür/args* işlevin adını ya da türünü `__clrcall` çağırmaya çalıştığınız işlevi.  İşlev işaretçisi çağrılırken bir türü kullanılır.

Yerel bir bağlamdan yönetilen bir işlevi çağırmak için çağıran bir "sarmalayıcı" işlev ekleyebilirsiniz `__clrcall` işlevi. Veya CLR sıralama mekanizması kullanabilirsiniz. bkz: [nasıl yapılır: hazırlama işlev işaretçileri PInvoke kullanarak](../../dotnet/how-to-marshal-function-pointers-using-pinvoke.md) daha fazla bilgi için.

Aşağıdaki örnek, C3642 oluşturur:

```
// C3642.cpp
// compile with: /clr
using namespace System;
struct S {
   void Test(String ^ s) {   // CLR type in signature, implicitly __clrcall
      Console::WriteLine(s);
   }
   void Test2(char * s) {
      Test(gcnew String(s));
   }
};

#pragma unmanaged
int main() {
   S s;
   s.Test("abc");   // C3642
   s.Test2("abc");   // OK
}
```