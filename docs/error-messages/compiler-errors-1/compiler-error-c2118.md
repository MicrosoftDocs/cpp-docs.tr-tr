---
title: Derleyici Hatası C2118
ms.date: 11/04/2016
f1_keywords:
- C2118
helpviewer_keywords:
- C2118
ms.assetid: bf4315d0-f085-4323-b813-96ee61a13bde
ms.openlocfilehash: 71b8273aaee52420f8a9c9c2dd2d015bea72ddf6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50465942"
---
# <a name="compiler-error-c2118"></a>Derleyici Hatası C2118

Negatif indis

Dizi boyutu tanımlama en fazla dizi boyutu daha büyük ya da sıfırdan küçük değerdir.

Aşağıdaki örnek, C2118 oluşturur:

```
// C2118.cpp
int main() {
   int array1[-1];   // C2118
   int array2[3];   // OK
}
```