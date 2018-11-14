---
title: Derleyici Hatası C3920
ms.date: 11/04/2016
f1_keywords:
- C3920
helpviewer_keywords:
- C3920
ms.assetid: 66e91f28-ed82-4ce2-bf22-c0c74905b1ed
ms.openlocfilehash: d7163cf07a440a0afd1216b3e5cf665326ffb963
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51522109"
---
# <a name="compiler-error-c3920"></a>Derleyici Hatası C3920

' operator'': bir sonek artırma/azaltma WinRT veya sonek arama CLR işleci tanımlanamaz WinRT veya CLR işleci, karşılık gelen önek çağıracaktır WinRT veya CLR işleci (op_Increment/op_Decrement), ancak sonek semantiğine sahip

Windows çalışma zamanı ve CLR sonek işlecini desteklemez ve kullanıcı tanımlı sonek işleçleri kullanılamaz.  Önek işleci tanımlayabilirsiniz ve önek işleci öncesi ve sonrası artırma işlemleri için kullanılır.

Aşağıdaki örnek, C3920 oluşturur ve bu sorunun nasıl gösterir:

```
// C3920.cpp
// compile with: /clr /LD
public value struct V {
   static V operator ++(V me, int)
   // try the following line instead
   // static V operator ++(V me)
   {   // C3920
      me.m_i++;
      return me;
   }

   int m_i;
};
```