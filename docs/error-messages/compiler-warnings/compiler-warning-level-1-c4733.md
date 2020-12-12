---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4733'
title: Derleyici Uyarısı (düzey 1) C4733
ms.date: 11/04/2016
f1_keywords:
- C4733
helpviewer_keywords:
- C4733
ms.assetid: 7ef4f577-772d-4b66-a7bf-8958a6b250bc
ms.openlocfilehash: e12e23830057404732aec641470cff5520818ef3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228631"
---
# <a name="compiler-warning-level-1-c4733"></a>Derleyici Uyarısı (düzey 1) C4733

Satır içi asm ' FS: 0 ' öğesine atanıyor: işleyici güvenli işleyici olarak kaydedilmedi

FS 'de değeri değiştiren bir işlev: 0 Yeni bir özel durum işleyici eklemek güvenli özel durumlarla çalışmayabilir, çünkü işleyici geçerli bir özel durum işleyicisi olarak kaydedilemeyebilir (bkz. [/SafeSEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md)).

Bu uyarıyı çözmek için, FS 'yi kaldırın: 0 Bu uyarıyı açın veya kapatın ve kullanın [. ](../../assembler/masm/dot-safeseh.md) Güvenli özel durum işleyicilerini belirtmek IÇIN SafeSEH.

Aşağıdaki örnek C4733 oluşturur:

```cpp
// C4733.cpp
// compile with: /W1 /c
// processor: x86
#include "stdlib.h"
#include "stdio.h"
void my_handler()
{
   printf("Hello from my_handler\n");
   exit(1);
}

int main()
{
   _asm {
      push    my_handler
      mov     eax, DWORD PTR fs:0
      push    eax
      mov     DWORD PTR fs:0, esp   // C4733
   }

   *(int*)0 = 0;
}
```
