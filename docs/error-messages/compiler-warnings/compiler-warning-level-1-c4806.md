---
title: Derleyici Uyarısı (düzey 1) C4806
ms.date: 11/04/2016
f1_keywords:
- C4806
helpviewer_keywords:
- C4806
ms.assetid: 79eb74cd-b925-4b5b-84e1-8ae6f33e38b3
ms.openlocfilehash: 0d3b0aa05ca5fff16b3cd28c11e3bf8290de1b3b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225351"
---
# <a name="compiler-warning-level-1-c4806"></a>Derleyici Uyarısı (düzey 1) C4806

' işlem ': güvenli olmayan işlem: ' Type ' türüne yükseltilen ' Type ' türünde hiçbir değer verilen sabite eşit olamaz

Bu ileti `b == 3` , türü olduğu gibi koda karşı uyarır `b` **`bool`** . Promosyon Kuralları ' **`bool`** ye yükseltilmelidir **`int`** . Bu geçerlidir, ancak hiçbir şekilde olamaz **`true`** . Aşağıdaki örnek C4806 oluşturur:

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
