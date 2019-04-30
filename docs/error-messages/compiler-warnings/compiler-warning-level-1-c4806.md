---
title: Derleyici Uyarısı (düzey 1) C4806
ms.date: 11/04/2016
f1_keywords:
- C4806
helpviewer_keywords:
- C4806
ms.assetid: 79eb74cd-b925-4b5b-84e1-8ae6f33e38b3
ms.openlocfilehash: b6fc5708d4e2f9982ceaab57260f13e134e4d247
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406411"
---
# <a name="compiler-warning-level-1-c4806"></a>Derleyici Uyarısı (düzey 1) C4806

'operation': Güvenli olmayan işlem: 'type 'type' türü için yükseltilen' türünde hiçbir değer belirtilen Sabitle eşit olabilir

Bu ileti karşı kodu gibi uyarır `b == 3`burada `b` türünde `bool`. Promosyon kurallarını neden `bool` yükseltilmesi için `int`. Bu yasal, ancak hiçbir zaman olabilir **true**. Aşağıdaki örnek, C4806 oluşturur:

```
// C4806.cpp
// compile with: /W1
int main()
{
   bool b = true;
   // try..
   // int b = true;

   if (b == 3)   // C4806
   {
      b = false;
   }
}
```