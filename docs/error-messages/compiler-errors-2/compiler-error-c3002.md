---
title: Derleyici Hatası C3002
ms.date: 11/04/2016
f1_keywords:
- C3002
helpviewer_keywords:
- C3002
ms.assetid: 2d4241a7-c8eb-4d43-a128-dca255d137bc
ms.openlocfilehash: 9f48021f5a32006c6a78a69500b0701cb7612d96
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300706"
---
# <a name="compiler-error-c3002"></a>Derleyici Hatası C3002

'name1 name2': birden fazla OpenMP yönergesi adı

Birden çok yönerge adlarına izin verilmemektedir.

Aşağıdaki örnek, C3002 oluşturur:

```
// C3002.c
// compile with: /openmp
int main()
{
   #pragma omp parallel single   // C3002
}
```