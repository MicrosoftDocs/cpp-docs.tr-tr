---
title: Derleyici Uyarısı (düzey 1) C4218
ms.date: 11/04/2016
f1_keywords:
- C4218
helpviewer_keywords:
- C4218
ms.assetid: d6c3cd90-4518-49e9-ae86-4ba9e2761d98
ms.openlocfilehash: 226bc91c272ff62ebe127aa190384d30a214b05d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223258"
---
# <a name="compiler-warning-level-1-c4218"></a>Derleyici Uyarısı (düzey 1) C4218

Standart olmayan uzantı kullanıldı: en az bir depolama sınıfı veya türü belirtilmelidir

Varsayılan Microsoft uzantılarıyla (/Ze), bir tür veya depolama sınıfı belirtmeden bir değişken bildirebilirsiniz. Varsayılan tür **`int`** .

## <a name="example"></a>Örnek

```cpp
// C4218.c
// compile with: /W4
i;  // C4218

int main()
{
}
```

Bu bildirimler, ANSI uyumluluğu ([/za](../../build/reference/za-ze-disable-language-extensions.md)) altında geçersizdir.
