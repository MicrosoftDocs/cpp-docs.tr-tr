---
title: Derleyici Uyarısı (düzey 1) C4669
ms.date: 11/04/2016
f1_keywords:
- C4669
helpviewer_keywords:
- C4669
ms.assetid: 97730679-e3dc-44d4-b2a8-aa65badc17f2
ms.openlocfilehash: f4d0b87c91649c5f2f6b5823fea82d2ce355d11a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374605"
---
# <a name="compiler-warning-level-1-c4669"></a>Derleyici Uyarısı (düzey 1) C4669

'cast': Güvenli olmayan dönüştürme: 'class' olan bir yönetilen veya WinRT türü nesne

Bir yayın, bir Windows çalışma zamanı veya yönetilen türü içeriyor. Derleyici, diğer bir işaretçi temelinde bir kopyasını gerçekleştirerek atama tamamlanır, ancak hiçbir diğer denetim sağlar. Bu uyarıyı çözmek için yönetilen üyeleri veya Windows çalışma zamanı türleri içeren sınıfları yapmayın.

Aşağıdaki örnek, C4669 oluşturur ve bu sorunun nasıl gösterir:

```
// C4669.cpp
// compile with: /clr /W1
ref struct A {
   int i;
   Object ^ pObj;   // remove the managed member to fix the warning
};

ref struct B {
   int j;
};

int main() {
   A ^ a = gcnew A;
   B ^ b = reinterpret_cast<B ^>(a);   // C4669
}
```