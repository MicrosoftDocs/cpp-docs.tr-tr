---
title: Derleyici Hatası C3019 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3019
dev_langs:
- C++
helpviewer_keywords:
- C3019
ms.assetid: 31a6d9b6-d29f-4499-9ad8-48dd751e87c7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e71f6741ba499855a4ac06ed578bd1f713e700dc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46046621"
---
# <a name="compiler-error-c3019"></a>Derleyici Hatası C3019

OpenMP 'for' deyimindeki artış hatalı biçimde

Bir OpenMP artırma parçası `for` hem sol ve sağ tarafındaki dizin değişkeni döngü kullanması gerekir.

Aşağıdaki örnek, C3019 oluşturur:

```
// C3019.cpp
// compile with: /openmp
int main()
{
   int i = 0, j = 1, n = 3;

   #pragma omp parallel
   {
      #pragma omp for
      for (i = 0; i < 10; i = j + n)   // C3019
      // Try the following line instead:
      // for (i = 0; i < 10; i++)
         j *= 2;
   }
}
```