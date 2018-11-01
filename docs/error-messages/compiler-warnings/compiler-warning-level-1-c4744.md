---
title: Derleyici Uyarısı (düzey 1) C4744
ms.date: 11/04/2016
f1_keywords:
- C4744
helpviewer_keywords:
- C4744
ms.assetid: f2a7d0b5-afd5-4926-abc3-cfbd367e3ff5
ms.openlocfilehash: 2118a32af8b99d35c1e1a6691561391ec5d2b8cc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50606017"
---
# <a name="compiler-warning-level-1-c4744"></a>Derleyici Uyarısı (düzey 1) C4744

'var', 'dosya1' ve 'dosya2' farklı türe sahip: 'type1' ve 'type2'

İki dosyalarında tanımlanan ya da başvurulan bir dış değişkenine bu dosyaları farklı türleri vardır.  Çözmek için aynı tür tanımlarını belirleyebilir veya dosyalardan biri değişken adını değiştirin.

/GL ile derlenmiş dosyalar yalnızca zaman C4744 yayıldığını  Daha fazla bilgi için [/GL (bütün Program iyileştirmesi)](../../build/reference/gl-whole-program-optimization.md).

> [!NOTE]
>  C++'ta bir değişken adı türü bilgilerini ile donatılmış olduğundan C4744 genellikle C (C++ değil) dosyalarında gerçekleşir.  (Aşağıda) örnek C++ derler olduğunda, bağlayıcı hatası LNK2019 elde edersiniz.

## <a name="example"></a>Örnek

Bu örnek, ilk tanımı içeriyor.

```
// C4744.c
// compile with: /c /GL
int global;
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4744 oluşturur.

```
// C4744b.c
// compile with: C4744.c /GL /W1
// C4744 expected
#include <stdio.h>

extern unsigned global;

main()
{
    printf_s("%d\n", global);
}
```