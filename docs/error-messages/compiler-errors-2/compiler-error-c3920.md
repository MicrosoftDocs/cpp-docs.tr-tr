---
title: Derleyici Hatası C3920 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3920
dev_langs:
- C++
helpviewer_keywords:
- C3920
ms.assetid: 66e91f28-ed82-4ce2-bf22-c0c74905b1ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3b85638907f350eb3545a858f1319e56b2459f09
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46112713"
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