---
title: Derleyici Hatası C3007
ms.date: 11/04/2016
f1_keywords:
- C3007
helpviewer_keywords:
- C3007
ms.assetid: e415ef42-bdc9-4f32-8198-5e25b289a089
ms.openlocfilehash: 551fb458ee02e29ae54aeb3382b2016da731808a
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345586"
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