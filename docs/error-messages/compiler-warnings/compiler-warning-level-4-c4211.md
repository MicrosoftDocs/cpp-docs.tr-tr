---
title: Derleyici Uyarısı (düzey 4) C4211
ms.date: 11/04/2016
f1_keywords:
- C4211
helpviewer_keywords:
- C4211
ms.assetid: 3eea3455-6faa-4cdb-8730-73db7026bd1f
ms.openlocfilehash: df19f90e17d6737a2639eb1245da197881e35c96
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218110"
---
# <a name="compiler-warning-level-4-c4211"></a>Derleyici Uyarısı (düzey 4) C4211

Standart olmayan uzantı kullanıldı: extern, static olarak yeniden tanımlandı

Varsayılan Microsoft uzantılarıyla (/Ze), bir **`extern`** tanımlayıcıyı olarak yeniden tanımlayabilirsiniz **`static`** .

## <a name="example"></a>Örnek

```c
// C4211.c
// compile with: /W4
extern int i;
static int i;   // C4211

int main()
{
}
```

Bu tür yeniden tanımlar, ANSI uyumluluğu ([/za](../../build/reference/za-ze-disable-language-extensions.md)) altında geçersizdir.
