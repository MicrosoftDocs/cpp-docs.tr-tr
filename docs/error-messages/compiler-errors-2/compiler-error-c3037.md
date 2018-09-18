---
title: Derleyici Hatası C3037 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3037
dev_langs:
- C++
helpviewer_keywords:
- C3037
ms.assetid: 9ba8a890-d3c7-4cce-93c5-d358e2bfad28
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3846aec8810e04813122a9c95c823fa99b3d698
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46089300"
---
# <a name="compiler-error-c3037"></a>Derleyici Hatası C3037

'var': 'reduction' yan tümcesindeki değişken kapsayan bağlamda paylaşılabilir olmalıdır

Belirtilen bir değişken bir [azaltma](../../parallel/openmp/reference/reduction.md) yan tümcesi her iş parçacığının bağlamında özel olabilir.

Aşağıdaki örnek, C3037 oluşturur:

```
// C3037.cpp
// compile with: /openmp /c
int g_i;

int main() {
   int i;

   #pragma omp parallel private(g_i)
   // try the following line instead
   // #pragma omp parallel
   {
      #pragma omp for reduction(+:g_i)   // C3037
      for (i = 0 ; i < 10 ; ++i) {
         g_i += i;
      }
   }
}
```