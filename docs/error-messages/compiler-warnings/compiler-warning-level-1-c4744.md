---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4744'
title: Derleyici Uyarısı (düzey 1) C4744
ms.date: 11/04/2016
f1_keywords:
- C4744
helpviewer_keywords:
- C4744
ms.assetid: f2a7d0b5-afd5-4926-abc3-cfbd367e3ff5
ms.openlocfilehash: d7be7c44d0e5abb1d0e3618ffa6ed1778a6410c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228462"
---
# <a name="compiler-warning-level-1-c4744"></a>Derleyici Uyarısı (düzey 1) C4744

' var ', ' FILE1 ' ve ' dosya2 ' içinde farklı türe sahip: ' type1 ' ve ' type2 '

İki dosyada başvurulan veya tanımlanan bir dış değişken bu dosyalardaki farklı türlere sahip.  Çözümlemek için, tür tanımlarını aynı yapın ya da dosyalardan birindeki değişken adını değiştirin.

C4744, yalnızca dosyalar/GLILE derlenmişse dağıtılır.  Daha fazla bilgi için bkz. [/GL (tüm program iyileştirmesi)](../../build/reference/gl-whole-program-optimization.md).

> [!NOTE]
> C++ bir değişken adı tür bilgileriyle donatılmış olduğundan, C4744 genellikle C (C++ değil) dosyalarında oluşur.  Örnek (aşağıdaki) C++ olarak derlendiğinde bağlayıcı hatası LNK2019 alırsınız.

## <a name="examples"></a>Örnekler

Bu örnek ilk tanımı içerir.

```c
// C4744.c
// compile with: /c /GL
int global;
```

Aşağıdaki örnek C4744 oluşturur.

```c
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
