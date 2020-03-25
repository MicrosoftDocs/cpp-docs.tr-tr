---
title: Derleyici Uyarısı (düzey 1) C4806
ms.date: 11/04/2016
f1_keywords:
- C4806
helpviewer_keywords:
- C4806
ms.assetid: 79eb74cd-b925-4b5b-84e1-8ae6f33e38b3
ms.openlocfilehash: 5895e9bf489e240b1eff6f1499b711047ea74b9b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175057"
---
# <a name="compiler-warning-level-1-c4806"></a>Derleyici Uyarısı (düzey 1) C4806

' işlem ': güvenli olmayan işlem: ' Type ' türüne yükseltilen ' Type ' türünde hiçbir değer verilen sabite eşit olamaz

Bu ileti, `b` tür `bool`olan `b == 3`gibi koda karşı uyarır. Promosyon kuralları `bool` `int`yükseltilmesine neden olur. Bu geçerlidir, ancak hiçbir şekilde **doğru**olmaz. Aşağıdaki örnek C4806 oluşturur:

```cpp
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
