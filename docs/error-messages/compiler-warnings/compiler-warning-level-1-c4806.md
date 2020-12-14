---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4806'
title: Derleyici Uyarısı (düzey 1) C4806
ms.date: 11/04/2016
f1_keywords:
- C4806
helpviewer_keywords:
- C4806
ms.assetid: 79eb74cd-b925-4b5b-84e1-8ae6f33e38b3
ms.openlocfilehash: 3e4aaa67c2a979afde2d1a7643d0c5ab1b879418
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97238251"
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
