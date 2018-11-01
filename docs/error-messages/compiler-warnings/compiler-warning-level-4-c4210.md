---
title: Derleyici Uyarısı (düzey 4) C4210
ms.date: 11/04/2016
f1_keywords:
- C4210
helpviewer_keywords:
- C4210
ms.assetid: f8600adf-dfe2-4022-a37a-3d4997641dfd
ms.openlocfilehash: 3435e18f60568cad390dcb0ef7900658a21ea959
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50638730"
---
# <a name="compiler-warning-level-4-c4210"></a>Derleyici Uyarısı (düzey 4) C4210

Standart olmayan uzantı kullanıldı: işleve dosya kapsamı verildi

Varsayılan Microsoft uzantılı ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)), işlev bildirimleri, dosya kapsamına sahip.

```
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

Bu uzantı, kodunuzun diğer derleyicileri için taşınabilir olmasını engelleyebilir.