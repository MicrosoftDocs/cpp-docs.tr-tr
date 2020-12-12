---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2655'
title: Derleyici hatası C2655
ms.date: 11/04/2016
f1_keywords:
- C2655
helpviewer_keywords:
- C2655
ms.assetid: beaefa6e-51b3-4df9-9150-960f3fbf40e0
ms.openlocfilehash: 113de213ab53892447666824c48510f7c9654d4e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286117"
---
# <a name="compiler-error-c2655"></a>Derleyici hatası C2655

' tanımlayıcı ': tanım veya yeniden bildirim geçerli kapsamda geçersizdir

Tanımlayıcı yalnızca genel kapsamda yeniden bildirilemez.

Aşağıdaki örnek C2655 oluşturur:

```cpp
// C2655.cpp
class A {};
class B {
public:
   static int i;
};

int B::i;  // OK

int main() {
   A B::i;  // C2655
}
```
