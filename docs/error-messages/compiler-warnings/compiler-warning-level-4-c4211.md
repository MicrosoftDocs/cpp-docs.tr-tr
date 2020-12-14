---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4211'
title: Derleyici Uyarısı (düzey 4) C4211
ms.date: 11/04/2016
f1_keywords:
- C4211
helpviewer_keywords:
- C4211
ms.assetid: 3eea3455-6faa-4cdb-8730-73db7026bd1f
ms.openlocfilehash: bbd6469dc98d95342538bf3a9065b4647619d69a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314743"
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
