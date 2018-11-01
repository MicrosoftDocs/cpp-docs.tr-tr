---
title: Derleyici Hatası C3920
ms.date: 11/04/2016
f1_keywords:
- C3920
helpviewer_keywords:
- C3920
ms.assetid: 66e91f28-ed82-4ce2-bf22-c0c74905b1ed
ms.openlocfilehash: e3c37cba4b7df2df9e9784b3a1afb8dbf9c8e8d9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50491734"
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