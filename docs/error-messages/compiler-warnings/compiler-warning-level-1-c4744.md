---
title: Derleyici Uyarısı (Düzey 1) C4744
ms.date: 11/04/2016
f1_keywords:
- C4744
helpviewer_keywords:
- C4744
ms.assetid: f2a7d0b5-afd5-4926-abc3-cfbd367e3ff5
ms.openlocfilehash: f932b1bcdf011678d4f85e0edf1e116a954b59fe
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367375"
---
# <a name="compiler-warning-level-1-c4744"></a>Derleyici Uyarısı (Düzey 1) C4744

'var' 'file1' ve 'file2'de farklı türdedir: 'type1' ve 'type2'

İki dosyada başvurulan veya tanımlanan harici bir değişkenin bu dosyalarda farklı türleri vardır.  Çözmek için, tür tanımlarını aynı hale getirin veya dosyalardan birinde değişken adını değiştirin.

C4744 yalnızca dosyalar /GL ile derlendiğinde yayılır.  Daha fazla bilgi için bkz: [/GL (Tüm Program Optimizasyonu)](../../build/reference/gl-whole-program-optimization.md).

> [!NOTE]
> C4744 genellikle C (C++değil) dosyalarında oluşur, çünkü C++'da bir değişken adı tür bilgileriyle dekore edilmiştir.  Örnek (aşağıda) C++ olarak derlendiğinde, lnk2019 bağlantı hatası alırsınız.

## <a name="example"></a>Örnek

Bu örnek ilk tanımı içerir.

```c
// C4744.c
// compile with: /c /GL
int global;
```

## <a name="example"></a>Örnek

Aşağıdaki örnek C4744 üretir.

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
