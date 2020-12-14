---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2334'
title: Derleyici hatası C2334
ms.date: 11/04/2016
f1_keywords:
- C2334
helpviewer_keywords:
- C2334
ms.assetid: 36142855-e00b-4bbf-80f5-a301edeff46e
ms.openlocfilehash: 875520c55550aa8507f28567b56b4fd83f53912a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234871"
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
