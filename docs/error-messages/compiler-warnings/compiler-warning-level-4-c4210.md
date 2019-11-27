---
title: Derleyici Uyarısı (düzey 4) C4210
ms.date: 11/04/2016
f1_keywords:
- C4210
helpviewer_keywords:
- C4210
ms.assetid: f8600adf-dfe2-4022-a37a-3d4997641dfd
ms.openlocfilehash: 5b27a711187af21dac093bdcc3e3af84502fe153
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541849"
---
# <a name="compiler-warning-level-4-c4210"></a>Derleyici Uyarısı (düzey 4) C4210

Standart olmayan uzantı kullanıldı: işleve dosya kapsamı verildi

Varsayılan Microsoft uzantıları ([/ze](../../build/reference/za-ze-disable-language-extensions.md)) ile, işlev bildirimlerinin dosya kapsamı vardır.

```c
// C4210.c
// compile with: /W4 /c
void func1()
{
   extern int func2( double );   // C4210 expected
}

int main()
{
   func2( 4 );   //  /Ze passes 4 as type double
}                //  /Za passes 4 as type int
```

Bu uzantı, kodunuzun diğer derleyicilere taşınabilir olmasını engelleyebilir.