---
title: Önemli hata C1310 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1310
dev_langs:
- C++
helpviewer_keywords:
- C1310
ms.assetid: ac48aa51-8023-42fe-b844-3f8bf228fbef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e2890177619500e7041d5edb0993789e244d17e4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46095592"
---
# <a name="fatal-error-c1310"></a>Önemli hata C1310

Profil temelli en iyileştirmeler OpenMP ile kullanılamaz

İle bağlamak mümkün olmayacaktır [/LTCG:PGI](../../build/reference/ltcg-link-time-code-generation.md) ile derlenmiş modüllerde [/GL](../../build/reference/gl-whole-program-optimization.md).

Aşağıdaki örnek, C1310 oluşturur:

```
// C1310.cpp
// compile with: /openmp /GL /link /LTCG:PGI
// C1310 expected
int main()
{
   int i = 0, j = 10;

   #pragma omp parallel
   {
      #pragma omp for
      for (i = 0; i < 0; i++)
         --j;
   }
}
```