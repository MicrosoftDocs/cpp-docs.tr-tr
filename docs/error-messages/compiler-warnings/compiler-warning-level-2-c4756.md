---
title: Derleyici Uyarısı (düzey 2) C4756
ms.date: 11/04/2016
f1_keywords:
- C4756
helpviewer_keywords:
- C4756
ms.assetid: 5a16df83-6b82-4619-83bd-319af4ef1d1d
ms.openlocfilehash: 640eb77273fdbda0b12bbf2c2a326e970951cbda
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051998"
---
# <a name="compiler-warning-level-2-c4756"></a>Derleyici Uyarısı (düzey 2) C4756

Sabit Aritmetikte taşma

Derleyici, derleme sırasında sabit aritmetik gerçekleştirirken bir özel durum oluşturdu.

Aşağıdaki örnek C4756 oluşturur:

```cpp
// C4756.cpp
// compile with: /W2 /Od
int main()
{
   float f = 1e100+1e100;   // C4756
}
```