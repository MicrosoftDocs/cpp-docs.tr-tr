---
title: Derleyici Hatası C2334
ms.date: 11/04/2016
f1_keywords:
- C2334
helpviewer_keywords:
- C2334
ms.assetid: 36142855-e00b-4bbf-80f5-a301edeff46e
ms.openlocfilehash: 4f068792193fd22ccddc39f9afc555e7c8672d8c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512986"
---
# <a name="compiler-error-c2334"></a>Derleyici Hatası C2334

Önceki beklenmeyen belirteçler ': veya {'; görünen işlev gövdesi atlanıyor

Aşağıdaki örnek, C2334 oluşturur. Hatası C2059 sonra bu hata oluşur:

```
// C2334.cpp
// compile with: /c
// C2059 expected
struct s1 {
   s1   {}   // C2334
   s1() {}   // OK
};
```