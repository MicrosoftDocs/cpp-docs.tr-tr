---
title: Derleyici Hatası C3006
ms.date: 11/04/2016
f1_keywords:
- C3006
helpviewer_keywords:
- C3006
ms.assetid: 449082ec-fd45-4c47-8ab3-ba6a719e4dc4
ms.openlocfilehash: 7200d0ab3b14a1f9faa310f466963d74f7c98985
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50436211"
---
# <a name="compiler-error-c3006"></a>Derleyici Hatası C3006

'yan tümcesi': OpenMP yönergesi, beklenen bağımsız değişken eksik'yönergesi ' yan tümcesi

Bir OpenMP yönergesinde beklenen bağımsız değişken yok.

Aşağıdaki örnek, C3006 oluşturur:

```
// C3006.c
// compile with: /openmp
int main()
{
   #pragma omp parallel shared   // C3006
   // Try the following line instead:
   // #pragma omp parallel shared(x) {}

}
```