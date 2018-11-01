---
title: Derleyici Uyarısı (düzey 1) C4945
ms.date: 11/04/2016
f1_keywords:
- C4945
helpviewer_keywords:
- C4945
ms.assetid: 6d2079ea-dc59-4611-bc68-9a22c06f7587
ms.openlocfilehash: 62dfbaed28f1afcdedb41d83158dfe4e8e0f61b6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50653862"
---
# <a name="compiler-warning-level-1-c4945"></a>Derleyici Uyarısı (düzey 1) C4945

'symbol': 'assembly2' değerinden simge alınamıyor: 'symbol', 'assembly1' başka bir derleme zaten alınmış olarak

Bir sembol başvurulan bir derleme içeri aktarıldı ancak bu simge başka bir başvurulan derleme zaten içeri aktarıldı. Değil bir derleme başvurusu veya derlemeleri biri değiştirilmiş sembol adını alın.

Aşağıdaki örnekler C4945 oluşturur.

```
// C4945a.cs
// compile with: /target:library
// C# source code to create a dll
public class ClassA {
   public int i;
}
```

Ardından,

```
// C4945b.cs
// compile with: /target:library
// C# source code to create a dll
public class ClassA {
   public int i;
}
```

Ardından,

```
// C4945c.cpp
// compile with: /clr /LD /W1
#using "C4945a.dll"
#using "C4945b.dll"   // C4945
```