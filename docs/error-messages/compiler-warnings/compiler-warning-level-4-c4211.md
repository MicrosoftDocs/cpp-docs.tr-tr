---
title: Derleyici Uyarısı (düzey 4) C4211
ms.date: 11/04/2016
f1_keywords:
- C4211
helpviewer_keywords:
- C4211
ms.assetid: 3eea3455-6faa-4cdb-8730-73db7026bd1f
ms.openlocfilehash: 6387f58430098e49e7add25e8915bf6b181634e9
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541838"
---
# <a name="compiler-warning-level-4-c4211"></a>Derleyici Uyarısı (düzey 4) C4211

Standart olmayan uzantı kullanıldı: extern, static olarak yeniden tanımlandı

Varsayılan Microsoft uzantıları (/Ze) ile bir `extern` tanımlayıcıyı **statik**olarak yeniden tanımlayabilirsiniz.

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
