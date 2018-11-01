---
title: Derleyici Uyarısı (düzey 4) C4211
ms.date: 11/04/2016
f1_keywords:
- C4211
helpviewer_keywords:
- C4211
ms.assetid: 3eea3455-6faa-4cdb-8730-73db7026bd1f
ms.openlocfilehash: f1e85591d8ec989d806eb43a6be99bdb1dc62fb4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50659335"
---
# <a name="compiler-warning-level-4-c4211"></a>Derleyici Uyarısı (düzey 4) C4211

Standart olmayan uzantı kullanıldı: extern, static yeniden tanımlandı

Varsayılan Microsoft uzantıları ile (/Ze), tanımlayabilirsiniz bir `extern` tanımlayıcı olarak **statik**.

## <a name="example"></a>Örnek

```
// C4211.c
// compile with: /W4
extern int i;
static int i;   // C4211

int main()
{
}
```

ANSI Uyumluluğu altında geçersiz tür yeniden tanımlaması ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).

## <a name="see-also"></a>Ayrıca Bkz.

