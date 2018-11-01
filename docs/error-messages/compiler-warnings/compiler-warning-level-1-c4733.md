---
title: Derleyici Uyarısı (düzey 1) C4733
ms.date: 11/04/2016
f1_keywords:
- C4733
helpviewer_keywords:
- C4733
ms.assetid: 7ef4f577-772d-4b66-a7bf-8958a6b250bc
ms.openlocfilehash: 0d0b0b912ef15294f9a4362a79dffd6d7eeabed8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50474926"
---
# <a name="compiler-warning-level-1-c4733"></a>Derleyici Uyarısı (düzey 1) C4733

Satır içi asm 'FS:0 için' atama: işleyici güvenli bir işleyici olarak kayıtlı değil

İşleyicinin geçerli özel durum işleyici olarak kayıtlı olmayabilir çünkü bir işlev yeni bir özel durum işleyicisi eklemek için FS:0 değerinde değişiklik güvenli özel durum ile birlikte çalışmayabilir (bkz [SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md)).

Bu uyarıyı çözmek için ya da FS:0 tanımı kaldırın veya bu uyarı açmak ve kullanmak [. SAFESEH](../../assembler/masm/dot-safeseh.md) güvenli özel durum işleyicileri belirtmek için.

Aşağıdaki örnek, C4733 oluşturur:

```
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