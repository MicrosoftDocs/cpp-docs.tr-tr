---
title: Derleyici Hatası C3642 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3642
dev_langs:
- C++
helpviewer_keywords:
- C3642
ms.assetid: 429790c2-9614-4d85-b31c-687c8d8f83ff
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: febd6f1a9a3b4bac8bbee59cbf8c5bead93c3fb3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047726"
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