---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2556'
title: Derleyici hatası C2556
ms.date: 11/04/2016
f1_keywords:
- C2556
helpviewer_keywords:
- C2556
ms.assetid: fc4399ad-45b3-49fd-be1f-0b13956a595a
ms.openlocfilehash: 6c2233e10e763e959511c6b435e0d894e921905a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134491"
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
