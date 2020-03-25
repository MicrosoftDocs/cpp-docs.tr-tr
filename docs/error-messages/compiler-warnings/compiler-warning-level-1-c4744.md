---
title: Derleyici Uyarısı (düzey 1) C4744
ms.date: 11/04/2016
f1_keywords:
- C4744
helpviewer_keywords:
- C4744
ms.assetid: f2a7d0b5-afd5-4926-abc3-cfbd367e3ff5
ms.openlocfilehash: 9f63da4acd87ef2bb0ba80df9e8c0e3e3db4bc79
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185652"
---
# <a name="compiler-warning-level-1-c4744"></a>Derleyici Uyarısı (düzey 1) C4744

' var ', ' FILE1 ' ve ' dosya2 ' içinde farklı türe sahip: ' type1 ' ve ' type2 '

İki dosyada başvurulan veya tanımlanan bir dış değişken bu dosyalardaki farklı türlere sahip.  Çözümlemek için, tür tanımlarını aynı yapın ya da dosyalardan birindeki değişken adını değiştirin.

C4744, yalnızca dosyalar/GLILE derlenmişse dağıtılır.  Daha fazla bilgi için bkz. [/GL (tüm program iyileştirmesi)](../../build/reference/gl-whole-program-optimization.md).

> [!NOTE]
>  Bir değişken adı tür bilgileriyle donatılmış olduğundan C++, C4744 genellikle C (Not) dosyalarında oluşur. C++  Örnek (aşağıdaki) olarak C++derlendiğinde BAĞLAYıCı hatası LNK2019 alırsınız.

## <a name="example"></a>Örnek

Bu örnek ilk tanımı içerir.

```c
// C4744.c
// compile with: /c /GL
int global;
```

## <a name="example"></a>Örnek

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
