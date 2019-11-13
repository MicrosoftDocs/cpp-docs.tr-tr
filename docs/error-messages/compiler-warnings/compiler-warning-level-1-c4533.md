---
title: Derleyici Uyarısı (düzey 1) C4533
ms.date: 11/04/2016
f1_keywords:
- C4533
helpviewer_keywords:
- C4533
ms.assetid: 359fecda-d540-46e5-b214-dbabe9ef50d2
ms.openlocfilehash: 6ee88af66238497216d7e5dab497394a58a55805
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73965758"
---
# <a name="compiler-warning-level-1-c4533"></a>Derleyici Uyarısı (düzey 1) C4533

' Variable ' öğesinin başlatılması ' yönerge ' tarafından atlandı

Programınızdaki bir yönerge denetim akışını değiştirdi, örneğin, bir değişken Başlatan bir yönerge yürütülmedi. Aşağıdaki örnek C4533 oluşturur:

```cpp
// C4533.cpp
// compile with: /W1
#include <stdio.h>

struct A
{
   int m_data;
};

int main()
{
   if (1)
   {
      goto Label;
   }

   A a = { 100 };

   Label:   // C4533
      printf("\n%d", a.m_data);   // prints an uninitialized value
}
```