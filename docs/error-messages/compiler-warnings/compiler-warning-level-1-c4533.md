---
title: Derleyici Uyarısı (düzey 1) C4533
ms.date: 11/04/2016
f1_keywords:
- C4533
helpviewer_keywords:
- C4533
ms.assetid: 359fecda-d540-46e5-b214-dbabe9ef50d2
ms.openlocfilehash: 20637dc23e13031b4199298a3374825062ce40da
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186432"
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
