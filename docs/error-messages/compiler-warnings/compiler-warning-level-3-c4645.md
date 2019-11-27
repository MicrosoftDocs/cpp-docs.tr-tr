---
title: Derleyici Uyarısı (düzey 3) C4645
ms.date: 11/04/2016
f1_keywords:
- C4645
helpviewer_keywords:
- C4645
ms.assetid: fd7c1ddf-f0d0-4e10-bab9-ccb4c3476298
ms.openlocfilehash: 4fa286f177284c03e5067b4af56f4e606b073653
ms.sourcegitcommit: 217fac22604639ebd62d366a69e6071ad5b724ac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/19/2019
ms.locfileid: "74189370"
---
# <a name="compiler-warning-level-3-c4645"></a>Derleyici Uyarısı (düzey 3) C4645

__declspec (noreturn) ile belirtilen işlevin dönüş bildirisi yok

[Noreturn](../../cpp/noreturn.md) `__declspec` değiştiricisi ile işaretlenmiş bir işlevde [Return](../../cpp/return-statement-in-program-termination-cpp.md) deyimleri bulundu. `return` deyimleri yoksayıldı.

Aşağıdaki örnek C4645 oluşturur:

```cpp
// C4645.cpp
// compile with:  /W3
void __declspec(noreturn) func() {
   return;   // C4645, delete this line to resolve
}

int main() {
}
```