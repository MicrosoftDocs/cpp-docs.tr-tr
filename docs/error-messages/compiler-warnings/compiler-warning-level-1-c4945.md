---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4945'
title: Derleyici Uyarısı (düzey 1) C4945
ms.date: 11/04/2016
f1_keywords:
- C4945
helpviewer_keywords:
- C4945
ms.assetid: 6d2079ea-dc59-4611-bc68-9a22c06f7587
ms.openlocfilehash: df05b0882b672f22428e9ddef0b195043cca7d2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327986"
---
# <a name="compiler-warning-level-1-c4945"></a>Derleyici Uyarısı (düzey 1) C4945

' symbol ': ' Assembly2 ' öğesinden sembol içeri aktarılamıyor: ' symbol ' zaten başka bir ' assembly1 ' derlemesinden içeri aktarılmış

Başvurulan bir derlemeden bir sembol içeri aktarıldı, ancak söz konusu sembol, başvurulan başka bir derlemeden zaten aktarılmış. Derlemelerden birine başvurmayın ya da derlemelerden birinde sembol adını değiştirmeyin.

Aşağıdaki örnekler C4945 oluşturur.

```csharp
// C4945a.cs
// compile with: /target:library
// C# source code to create a dll
public class ClassA {
   public int i;
}
```

ardından,

```csharp
// C4945b.cs
// compile with: /target:library
// C# source code to create a dll
public class ClassA {
   public int i;
}
```

ardından,

```cpp
// C4945c.cpp
// compile with: /clr /LD /W1
#using "C4945a.dll"
#using "C4945b.dll"   // C4945
```
