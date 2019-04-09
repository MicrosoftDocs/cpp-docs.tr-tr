---
title: Derleyici Uyarısı (düzey 4) C4211
ms.date: 11/04/2016
f1_keywords:
- C4211
helpviewer_keywords:
- C4211
ms.assetid: 3eea3455-6faa-4cdb-8730-73db7026bd1f
ms.openlocfilehash: 6d61191c4a7ed950d979158ccdfa3a390439b019
ms.sourcegitcommit: 35c4b3478f8cc310ebbd932a18963ad8ab846ed9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59237100"
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
