---
title: Derleyici Uyarısı (düzey 3) C4645
ms.date: 11/04/2016
f1_keywords:
- C4645
helpviewer_keywords:
- C4645
ms.assetid: fd7c1ddf-f0d0-4e10-bab9-ccb4c3476298
ms.openlocfilehash: 607122b5592c9db4fc2ad4cabf369b4605b2673b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228771"
---
# <a name="compiler-warning-level-3-c4645"></a>Derleyici Uyarısı (düzey 3) C4645

__declspec (noreturn) ile belirtilen işlevin dönüş bildirisi yok

[Noreturn](../../cpp/noreturn.md) değiştiricisi ile işaretlenmiş bir işlevde [Return](../../cpp/return-statement-in-program-termination-cpp.md) deyimleri bulundu **`__declspec`** . **`return`** İfade yoksayıldı.

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
