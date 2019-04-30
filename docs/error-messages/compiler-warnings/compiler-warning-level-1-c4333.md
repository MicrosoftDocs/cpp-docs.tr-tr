---
title: Derleyici Uyarısı (düzey 1) C4333
ms.date: 11/04/2016
f1_keywords:
- C4333
helpviewer_keywords:
- C4333
ms.assetid: d3763c52-6110-4da0-84db-5264e3f3f166
ms.openlocfilehash: b0f87b5d839dcfbb577af567a1a51a95daf716f0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406606"
---
# <a name="compiler-warning-level-1-c4333"></a>Derleyici Uyarısı (düzey 1) C4333

'operator': veri kaybı olan çok fazla miktarda sağa kaydırma

Bir çok fazla miktarda sağa kaydırma işlemi oluştu.  Tüm önemli bitlerin çıkış yaptı ve sonuç her zaman sıfır olacaktır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4333 oluşturur.

```
// C4333.cpp
// compile with: /c /W1
unsigned shift8 (unsigned char c) {
   return c >> 8;   // C4333

   // try the following line instead
   // return c >> 4;   // OK
}
```