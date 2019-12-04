---
title: Derleyici hatası C3846
ms.date: 11/04/2016
f1_keywords:
- C3846
helpviewer_keywords:
- C3846
ms.assetid: c470f8a5-106b-4efb-b8dc-e1319e04130f
ms.openlocfilehash: a4c51ccfc724cf8309044812b287677f0f1a2ff0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754907"
---
# <a name="compiler-error-c3846"></a>Derleyici hatası C3846

' symbol ': ' Assembly2 ' öğesinden sembol içeri aktarılamıyor: ' symbol ' zaten başka bir ' assembly1 ' derlemesinden içeri aktarılmış

Başvurulan bir derlemeden daha önce içeri aktarıldığından, bir sembol başvurulan derlemeden içeri aktarılamadı.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3846 oluşturur:

```cpp
// C3846a.cpp
// compile with: /LD /clr
public ref struct G
{
};
```

Ardından bunu derleyin:

```cpp
// C3846b.cpp
// compile with: /clr
#using "c3846a.dll"
#using "c3846a.obj"   // C3846

int main()
{
}
```
