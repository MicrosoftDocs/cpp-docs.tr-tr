---
title: Derleyici hatası C2334
ms.date: 11/04/2016
f1_keywords:
- C2334
helpviewer_keywords:
- C2334
ms.assetid: 36142855-e00b-4bbf-80f5-a301edeff46e
ms.openlocfilehash: f8a096a89bdb076b857e5adc49ad8162551612f2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74747702"
---
# <a name="compiler-error-c2334"></a>Derleyici hatası C2334

': veya {' öncesinde beklenmeyen belirteçler; görünen işlev gövdesi atlanıyor

Aşağıdaki örnek C2334 oluşturur. Hata C2059 sonra bu hata oluşur:

```cpp
// C2334.cpp
// compile with: /c
// C2059 expected
struct s1 {
   s1   {}   // C2334
   s1() {}   // OK
};
```
