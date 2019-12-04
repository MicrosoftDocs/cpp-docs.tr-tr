---
title: Derleyici hatası C2120
ms.date: 11/04/2016
f1_keywords:
- C2120
helpviewer_keywords:
- C2120
ms.assetid: b0f3f66c-6cd2-4f48-9ea3-c270b53c2b8c
ms.openlocfilehash: 6b188f4f3e898a17a5f8fbeafaa2d1c3c6e08552
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737978"
---
# <a name="compiler-error-c2120"></a>Derleyici hatası C2120

' void ' tüm türlerle geçersizdir

`void` türü, başka bir türe sahip bir bildirimde kullanılır.

Aşağıdaki örnek C2120 oluşturur:

```cpp
// C2120.cpp
int main() {
   void int i;   // C2120
   int j;   // OK
}
```
