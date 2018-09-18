---
title: Derleyici Hatası C3007 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3007
dev_langs:
- C++
helpviewer_keywords:
- C3007
ms.assetid: e415ef42-bdc9-4f32-8198-5e25b289a089
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 70e580da61c3314978a071233a576049de2d83b2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054707"
---
# <a name="compiler-error-c3007"></a>Derleyici Hatası C3007

'değişken': OpenMP 'yönergesi' yönergesindeki yan tümce bağımsız değişken almaz

Bağımsız değişken bir OpenMP yönergesinde gerekiyordu, ancak yönergesi bir bağımsız değişken almaz.

Aşağıdaki örnek, C3007 oluşturur:

```
// C3007.c
// compile with: /openmp
int main()
{
   #pragma omp parallel for ordered(2)   // C3007
}
```