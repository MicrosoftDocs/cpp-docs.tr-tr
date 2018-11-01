---
title: Derleyici Hatası C3274
ms.date: 11/04/2016
f1_keywords:
- C3274
helpviewer_keywords:
- C3274
ms.assetid: 1f03f18e-b569-48eb-9249-11c70122a305
ms.openlocfilehash: a44a7d471e7e079ee43afa8bf58fd590be2f4bf8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50506671"
---
# <a name="compiler-error-c3274"></a>Derleyici Hatası C3274

__finally/finally olmadan eşleşen deneyin

A [__finally](../../cpp/try-finally-statement.md) veya [son](../../dotnet/finally.md) deyimi, bir eşleştirme olmadan bulundu `try`. Bu sorunu çözmek için ya da silme `__finally` deyimi veya ekleme bir `try` bildirimi `__finally`.

Aşağıdaki örnek, C3274 oluşturur:

```
// C3274.cpp
// compile with: /clr
// C3274 expected
using namespace System;
int main() {
   try {
      try {
         throw gcnew ApplicationException();
      }
      catch(...) {
         Console::Error->WriteLine(L"Caught an exception");
      }
      finally {
         Console::WriteLine(L"In finally");
      }
   } finally {
      Console::WriteLine(L"In finally");
   }

   // Uncomment the following 3 lines to resolve.
   // try {
   //   throw gcnew ApplicationException();
   // }

   finally {
      Console::WriteLine(L"In finally");
   }
   Console::WriteLine(L"**FAIL**");
}
```