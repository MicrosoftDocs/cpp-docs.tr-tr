---
title: Derleyici Uyarısı (düzey 3) C4645
ms.date: 11/04/2016
f1_keywords:
- C4645
helpviewer_keywords:
- C4645
ms.assetid: fd7c1ddf-f0d0-4e10-bab9-ccb4c3476298
ms.openlocfilehash: 246eed6592b892c3bd233d9217e26e7bf7a49ff8
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91502313"
---
# <a name="compiler-warning-level-3-c4645"></a>Derleyici Uyarısı (düzey 3) C4645

__declspec (noreturn) ile belirtilen işlevin dönüş bildirisi yok

[Noreturn](../../cpp/noreturn.md) değiştiricisi ile işaretlenmiş bir işlevde [Return](../../cpp/program-termination.md) deyimleri bulundu **`__declspec`** . **`return`** İfade yoksayıldı.

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
