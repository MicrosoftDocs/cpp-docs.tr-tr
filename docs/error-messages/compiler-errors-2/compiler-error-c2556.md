---
title: Derleyici hatası C2556
ms.date: 11/04/2016
f1_keywords:
- C2556
helpviewer_keywords:
- C2556
ms.assetid: fc4399ad-45b3-49fd-be1f-0b13956a595a
ms.openlocfilehash: 6b6f08ac52eff355f0857968817a681818e3c3dc
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756779"
---
# <a name="compiler-error-c2556"></a>Derleyici hatası C2556

' tanımlayıcı ': aşırı yüklenmiş işlevler yalnızca dönüş türüne göre farklılık gösterir

Aşırı yüklenmiş işlevlerde farklı dönüş türleri, ancak aynı parametre listesi var. Her aşırı yüklenmiş işlevin ayrı bir biçimsel parametre listesi olmalıdır.

Aşağıdaki örnek C2556 oluşturur:

```cpp
// C2556.cpp
// compile with: /c
class C {
   int func();
   double func();   // C2556
   int func(int i);   // ok parameter lists differ
};
```
