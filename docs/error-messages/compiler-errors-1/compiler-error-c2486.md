---
title: Derleyici Hatası C2486
ms.date: 11/04/2016
f1_keywords:
- C2486
helpviewer_keywords:
- C2486
ms.assetid: 436da349-6461-4e32-bfca-4f3e620108e2
ms.openlocfilehash: 8d745c03530f331da83b45c765a2cb4bb7d76d8e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555667"
---
# <a name="compiler-error-c2486"></a>Derleyici Hatası C2486

'__Local_sıze' yalnızca 'naked' özniteliği olan işlevde izin verilir

Satır içi derleme işlevlerindeki adı `__LOCAL_SIZE` bildirilen işlevler için ayrılmış [naked](../../cpp/naked-cpp.md) özniteliği.

Aşağıdaki örnek, C2486 oluşturur:

```
// C2486.cpp
// processor: x86
void __declspec(naked) f1() {
   __asm {
      mov   eax,   __LOCAL_SIZE
   }
}
void f2() {
   __asm {
      mov   eax,   __LOCAL_SIZE   // C2486
   }
}
```