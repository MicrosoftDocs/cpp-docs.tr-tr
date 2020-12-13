---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2486'
title: Derleyici hatası C2486
ms.date: 11/04/2016
f1_keywords:
- C2486
helpviewer_keywords:
- C2486
ms.assetid: 436da349-6461-4e32-bfca-4f3e620108e2
ms.openlocfilehash: c45e0bdb0f515743694fe372bea3afdb24e00177
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339364"
---
# <a name="compiler-error-c2486"></a>Derleyici hatası C2486

' __LOCAL_SIZE ' öğesine yalnızca ' Naked ' özniteliği olan işlevde izin verilir

Satır içi derleme işlevlerinde ad, `__LOCAL_SIZE` [Naked](../../cpp/naked-cpp.md) özniteliğiyle belirtilen işlevler için ayrılmıştır.

Aşağıdaki örnek C2486 oluşturur:

```cpp
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
