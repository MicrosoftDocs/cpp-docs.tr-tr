---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3002'
title: Derleyici hatası C3002
ms.date: 11/04/2016
f1_keywords:
- C3002
helpviewer_keywords:
- C3002
ms.assetid: 2d4241a7-c8eb-4d43-a128-dca255d137bc
ms.openlocfilehash: 00984b6d3ed0845dd532f82462d9c44f6893a846
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326062"
---
# <a name="compiler-error-c3002"></a>Derleyici hatası C3002

' name1 AD2 ': birden fazla OpenMP yönergesi adı

Birden çok yönerge adına izin verilmez.

Aşağıdaki örnek C3002 oluşturur:

```c
// C3002.c
// compile with: /openmp
int main()
{
   #pragma omp parallel single   // C3002
}
```
