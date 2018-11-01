---
title: Derleyici Uyarısı (Düzey 2) C4756
ms.date: 11/04/2016
f1_keywords:
- C4756
helpviewer_keywords:
- C4756
ms.assetid: 5a16df83-6b82-4619-83bd-319af4ef1d1d
ms.openlocfilehash: 0e4e0d5e227795a45eb22e3fcb17bdfa600d69e9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622527"
---
# <a name="compiler-warning-level-2-c4756"></a>Derleyici Uyarısı (Düzey 2) C4756

Sabit aritmetikte taşma

Derleyici, derleme sırasında sabit aritmetik yaparken bir özel durum oluşturdu.

Aşağıdaki örnek, C4756 oluşturur:

```
// C4756.cpp
// compile with: /W2 /Od
int main()
{
   float f = 1e100+1e100;   // C4756
}
```