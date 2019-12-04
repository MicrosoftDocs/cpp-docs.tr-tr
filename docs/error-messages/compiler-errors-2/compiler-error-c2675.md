---
title: Derleyici hatası C2675
ms.date: 11/04/2016
f1_keywords:
- C2675
helpviewer_keywords:
- C2675
ms.assetid: 4b92a12b-bff8-4dd5-a109-620065fc146c
ms.openlocfilehash: 0b7b81ce7314fbad02d6873403fc5cf1bdd54709
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760380"
---
# <a name="compiler-error-c2675"></a>Derleyici hatası C2675

Birli ' operator ': ' Type ' Bu işleci veya önceden tanımlanmış işleç için kabul edilebilir bir türe dönüştürmeyi tanımlamıyor

C2675, birli bir operatör kullanılırken da gerçekleşebilir ve tür işleci veya önceden tanımlanmış işleç için kabul edilebilir bir türe dönüştürmeyi tanımlamaz. İşlecini kullanmak için, belirtilen tür için onu tekrar yüklemelisiniz veya işlecin tanımlandığı bir türe dönüştürme tanımlamanız gerekir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2675 oluşturur.

```cpp
// C2675.cpp
struct C {
   C(){}
} c;

struct D {
   D(){}
   void operator-(){}
} d;

int main() {
   -c;   // C2675
   -d;   // OK
}
```
