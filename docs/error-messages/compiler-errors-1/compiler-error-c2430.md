---
title: Derleyici hatası C2430
ms.date: 11/04/2016
f1_keywords:
- C2430
helpviewer_keywords:
- C2430
ms.assetid: 07c20f76-63e1-4d22-b2a9-98b0d45c5cac
ms.openlocfilehash: f82eb4914ec36aa513822964f551a05fbb77aa97
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744582"
---
# <a name="compiler-error-c2430"></a>Derleyici hatası C2430

' Identifier ' içinde birden fazla dizin yazmacı

Birden çok kayıt ölçeklendirilir. Derleyici ölçeklendirilmiş Dizin oluşturmayı destekler, ancak yalnızca bir kaydı ölçeklendirebilirsiniz.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2430 oluşturur.

```cpp
// C2430.cpp
// processor: x86
int main() {
   _asm mov eax, [ebx*2+ecx*4] // C2430
}
```
