---
title: Derleyici Hatası C2869
ms.date: 11/04/2016
f1_keywords:
- C2869
helpviewer_keywords:
- C2869
ms.assetid: 6e30c001-47f3-4101-b9f1-cc542c9fffae
ms.openlocfilehash: 38ac73484814e0089b412938ffc2776872deff3e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50614454"
---
# <a name="compiler-error-c2869"></a>Derleyici Hatası C2869

'name': bir ad alanı olarak zaten tanımlandı

Zaten bir ad alanı olarak kullanılan bir adı yeniden kullanamazsınız.

Aşağıdaki örnek, C2869 oluşturur:

```
// C2869.cpp
// compile with: /c
namespace A { int i; };

class A {};   // C2869, A is already used
```