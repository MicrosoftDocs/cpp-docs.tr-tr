---
title: Derleyici hatası C3002
ms.date: 11/04/2016
f1_keywords:
- C3002
helpviewer_keywords:
- C3002
ms.assetid: 2d4241a7-c8eb-4d43-a128-dca255d137bc
ms.openlocfilehash: 677c88747198a2ac95a84e788a5fd16456b6372b
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302204"
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
