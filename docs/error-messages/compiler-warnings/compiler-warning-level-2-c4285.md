---
title: Derleyici Uyarısı (Düzey 2) C4285
ms.date: 11/04/2016
f1_keywords:
- C4285
helpviewer_keywords:
- C4285
ms.assetid: fa14de1f-fc19-4eec-8bea-81003636e12f
ms.openlocfilehash: 96e1077ce3c9e60823a11aa41719738265ee703b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50535986"
---
# <a name="compiler-warning-level-2-c4285"></a>Derleyici Uyarısı (Düzey 2) C4285

'-> identifier::operator için' dönüş türü içtakı gösterimi kullanılırsa özyinelemelidir

Belirtilen **-> () işleci** işlev dönüş türü olamaz, tanımlanan veya kendisi için tanımlanmış olduğu tür başvurusu.

Aşağıdaki örnek, C4285 oluşturur:

```
// C4285.cpp
// compile with: /W2
class C
{
public:
    C operator->();   // C4285
   // C& operator->();  C4285, also
};

int main()
{
}
```