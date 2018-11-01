---
title: Derleyici Hatası C3848
ms.date: 11/04/2016
f1_keywords:
- C3848
helpviewer_keywords:
- C3848
ms.assetid: 32d3ccef-01ec-4f8b-bbff-fb9b1a76b4c4
ms.openlocfilehash: 1d738311ada14999a5345a4e2394631254dda00a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50448328"
---
# <a name="compiler-error-c3848"></a>Derleyici Hatası C3848

ifade türü 'type' olan 'function' çağırmak için bazı const-volatile niteleyicileri kaybeder

Belirtilen bir const-volatile türüne sahip bir değişken, yalnızca üye ile aynı veya daha büyük const-volatile nitelikleri tanımlanan işlevleri çağırabilir.

Aşağıdaki örnekler C3848 oluştur:

```
// C3848.cpp
void glbFunc1()
{
}

typedef void (* pFunc1)();

struct S3
{
   operator pFunc1() // const
   {
      return &glbFunc1;
   }
};

int main()
{
   const S3 s3;
   s3();   // C3848, uncomment const qualifier
}
```