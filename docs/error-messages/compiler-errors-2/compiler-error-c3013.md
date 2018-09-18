---
title: Derleyici Hatası C3013 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3013
dev_langs:
- C++
helpviewer_keywords:
- C3013
ms.assetid: f896777d-27e6-4b6d-baab-1567317f3374
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4b605cdf090dea66507696f8ac7e9a00dce11c0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049779"
---
# <a name="compiler-error-c3013"></a>Derleyici Hatası C3013

'yan tümcesi': yan tümcesi yalnızca görüntülenebilir kez OpenMP 'yönergesi' yönergesinde

Bir yan tümcesi aynı yönergesinde iki kez görüldü. Yan tümcesi bir örneğini silin.

Aşağıdaki örnek, C3013 oluşturur:

```
// C3013.cpp
// compile with: /openmp
int main() {
   int a, b, c, x, y, z;

   #pragma omp parallel shared(a,b,c) private(x)

   #pragma omp for nowait private(x) nowait   // C3013
   // The previous line generates C3013, with two nowait clauses
   // try the following line instead:
   // #pragma omp for nowait private(x)
   for (a = 0 ; a < 10 ; ++a) {
   }
}
```