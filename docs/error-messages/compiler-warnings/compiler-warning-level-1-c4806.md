---
title: Derleyici Uyarısı (düzey 1) C4806 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4806
dev_langs:
- C++
helpviewer_keywords:
- C4806
ms.assetid: 79eb74cd-b925-4b5b-84e1-8ae6f33e38b3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b580500c3887fe60b7864280ad5ca1804752f2ae
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062611"
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