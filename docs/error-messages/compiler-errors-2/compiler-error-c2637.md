---
title: Derleyici hatası C2637
ms.date: 11/04/2016
f1_keywords:
- C2637
helpviewer_keywords:
- C2637
ms.assetid: 58d94447-eb96-4d8f-a690-dd78d322462e
ms.openlocfilehash: a17bd95cf1727d058e0cbd9e3dfb93c500da9fb5
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758261"
---
# <a name="compiler-error-c2637"></a>Derleyici hatası C2637

' tanımlayıcı ': veri üyelerine yönelik işaretçiler değiştirilemez

Veri üyesine yönelik işaretçinin çağrı kuralı olamaz. Çözümlemek için, çağırma kuralını kaldırın ya da üye işlevine bir işaretçi bildirin.

Aşağıdaki örnek C2637 oluşturur:

```cpp
// C2637.cpp
// compile with: /c
struct S {};
int __stdcall S::*pms1;   // C2637

// OK
int S::*pms2;
int (__stdcall S::*pms3)(...);
```
