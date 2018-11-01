---
title: Derleyici Uyarısı (düzey 1) C4218
ms.date: 11/04/2016
f1_keywords:
- C4218
helpviewer_keywords:
- C4218
ms.assetid: d6c3cd90-4518-49e9-ae86-4ba9e2761d98
ms.openlocfilehash: 36d5de3b1270b41edfc391df960a556aca207709
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555304"
---
# <a name="compiler-warning-level-1-c4218"></a>Derleyici Uyarısı (düzey 1) C4218

Standart olmayan uzantı kullanıldı: en az bir depolama sınıfı veya türü belirtmeniz gerekir

Varsayılan Microsoft Uzantıları (/Ze) ile bir türü veya depolama sınıfı belirtmeden bir değişken bildirebilir. Varsayılan türü `int`.

## <a name="example"></a>Örnek

```
// C4218.c
// compile with: /W4
i;  // C4218

int main()
{
}
```

Bu tür bildirimleri ANSI Uyumluluğu altında geçersiz ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).