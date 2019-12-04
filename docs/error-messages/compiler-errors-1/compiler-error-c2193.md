---
title: Derleyici hatası C2193
ms.date: 11/04/2016
f1_keywords:
- C2193
helpviewer_keywords:
- C2193
ms.assetid: 9813e853-d581-4f51-bb75-4e242298a844
ms.openlocfilehash: 25ebfc73fb46eca3a27875075af2d4ed46ed2fef
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758560"
---
# <a name="compiler-error-c2193"></a>Derleyici hatası C2193

' tanımlayıcı ': zaten bir kesimde

Bir işlev, `alloc_text` ve `code_seg` pragmaları kullanılarak iki farklı parçaya yerleştirildi.

Aşağıdaki örnek C2193 oluşturur:

```cpp
// C2193.cpp
// compile with: /c
extern "C" void MYFUNCTION();
#pragma alloc_text(MYCODE, MYFUNCTION)
#pragma code_seg("MYCODE2")
extern "C" void MYFUNCTION() {}   // C2193
extern "C" void MYFUNCTION2() {}
```
