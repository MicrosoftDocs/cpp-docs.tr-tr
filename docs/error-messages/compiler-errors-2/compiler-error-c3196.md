---
title: Derleyici Hatası C3196
ms.date: 11/04/2016
f1_keywords:
- C3196
helpviewer_keywords:
- C3196
ms.assetid: d9c38a13-191d-472d-aa2b-f61a6459d16c
ms.openlocfilehash: 252fef18fa98183dcc75219c1b802461f3bd2833
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50517058"
---
# <a name="compiler-error-c3196"></a>Derleyici Hatası C3196

'anahtar sözcüğü': birden fazla kez kullanıldı

Bir anahtar sözcük birden çok kez kullanıldı.

Aşağıdaki örnek, C3196 oluşturur:

```
// C3196.cpp
// compile with: /clr
ref struct R abstract abstract {};   // C3196
ref struct S abstract {};   // OK
```