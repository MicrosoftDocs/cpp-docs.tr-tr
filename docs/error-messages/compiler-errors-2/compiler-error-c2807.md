---
title: Derleyici Hatası C2807
ms.date: 11/04/2016
f1_keywords:
- C2807
helpviewer_keywords:
- C2807
ms.assetid: bd7a207a-f379-4de6-8ee8-c7cab78b3480
ms.openlocfilehash: 5e3fd05b1c2473efbc1cd102056c73b2f221981d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50527939"
---
# <a name="compiler-error-c2807"></a>Derleyici Hatası C2807

'operator işleci' sonekinin ikinci biçimsel parametresi 'int' olmalıdır

Sonek operatörü için ikinci parametre yanlış türde.

Aşağıdaki örnek, C2807 oluşturur:

```
// C2807.cpp
// compile with: /c
class X {
public:
   X operator++ ( X );   // C2807 nonvoid parameter
   X operator++ ( int );   // OK, int parameter
};
```