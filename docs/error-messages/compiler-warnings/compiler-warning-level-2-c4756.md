---
title: Derleyici Uyarısı (Düzey 2) C4756
ms.date: 11/04/2016
f1_keywords:
- C4756
helpviewer_keywords:
- C4756
ms.assetid: 5a16df83-6b82-4619-83bd-319af4ef1d1d
ms.openlocfilehash: 0e4e0d5e227795a45eb22e3fcb17bdfa600d69e9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402430"
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