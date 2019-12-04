---
title: Derleyici hatası C2423
ms.date: 11/04/2016
f1_keywords:
- C2423
helpviewer_keywords:
- C2423
ms.assetid: 8797fb8b-b58b-4add-b6e6-2a9a3cd9084d
ms.openlocfilehash: 29203d3816f82bce95be656fdf71cb6536b325b9
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744673"
---
# <a name="compiler-error-c2423"></a>Derleyici hatası C2423

' number ': geçersiz ölçek

Satır içi derleme kodu, bir kaydı ölçeklendirmek için 1, 2, 4 veya 8 dışında bir sayı kullanır.

Aşağıdaki örnek C2423 oluşturur:

```cpp
// C2423.cpp
// processor: x86
int main() {
   _asm {
      lea EAX, [EAX*3]   // C2423
      lea EAX, [EAX+EAX*2]   // OK
   }
}
```
