---
title: Derleyici hatası C3920
ms.date: 11/04/2016
f1_keywords:
- C3920
helpviewer_keywords:
- C3920
ms.assetid: 66e91f28-ed82-4ce2-bf22-c0c74905b1ed
ms.openlocfilehash: 416752054f7397a058329e1ee4bdaef693dd0d28
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758469"
---
# <a name="compiler-error-c3920"></a>Derleyici hatası C3920

' operator ' ': sonek artırma/azaltma WinRT veya CLR işleci, sonek WinRT veya clr işlecini çağırmak için karşılık gelen ön ek WinRT veya CLR işleci (op_Increment/op_Decrement) veya sonek semantiğinin çağrılması

Windows Çalışma Zamanı ve CLR sonek işlecini desteklemez ve Kullanıcı tanımlı sonek işleçlerine izin verilmez.  Bir önek işleci tanımlayabilir ve ön ve sonrası işlemleri için önek işleci kullanılacaktır.

Aşağıdaki örnek C3920 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
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
