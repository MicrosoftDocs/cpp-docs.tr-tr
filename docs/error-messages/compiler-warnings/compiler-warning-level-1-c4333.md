---
title: Derleyici Uyarısı (düzey 1) C4333
ms.date: 11/04/2016
f1_keywords:
- C4333
helpviewer_keywords:
- C4333
ms.assetid: d3763c52-6110-4da0-84db-5264e3f3f166
ms.openlocfilehash: 0b4e567f07d15b47d3c1f507b43257dac9a49d66
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966047"
---
# <a name="compiler-warning-level-1-c4333"></a>Derleyici Uyarısı (düzey 1) C4333

' operator ': çok büyük miktarda sağa kaydırma, veri kaybı

Sağa kaydırma işlemi çok büyük bir miktar oluştu.  Tüm önemli bitleri aşağı kaydırır ve sonuç her zaman sıfır olur.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4333 oluşturur.

```cpp
// C4333.cpp
// compile with: /c /W1
unsigned shift8 (unsigned char c) {
   return c >> 8;   // C4333

   // try the following line instead
   // return c >> 4;   // OK
}
```