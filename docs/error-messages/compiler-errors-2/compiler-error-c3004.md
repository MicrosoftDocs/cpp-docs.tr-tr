---
title: Derleyici Hatası C3004
ms.date: 11/04/2016
f1_keywords:
- C3004
helpviewer_keywords:
- C3004
ms.assetid: 819c2b57-8366-4ca7-9135-1f0c5e5b6bb6
ms.openlocfilehash: 88f781f8cb3e661998651bb4b1a7b0d54b183a0a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50657194"
---
# <a name="compiler-error-c3004"></a>Derleyici Hatası C3004

'yan tümcesi': yan tümce OpenMP 'yönergesi' yönergesinde geçerli değil

Bir OpenMP tümcesi için etkin bir yönergesinde kullanıldı.

Aşağıdaki örnek, C3004 oluşturur:

```
// C3004.c
// compile with: /openmp
int main()
{
   int x, y, z;

   // Shared clause not allowed for 'single' directive.
   #pragma omp single shared(x, y)   // C3004

   x = y;
}
```