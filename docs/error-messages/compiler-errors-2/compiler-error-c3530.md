---
title: Derleyici Hatası C3530
ms.date: 11/04/2016
f1_keywords:
- C3530
helpviewer_keywords:
- C3530
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
ms.openlocfilehash: 90f6000c7d4c4bfa0d610bd5942df0b958e47c60
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643636"
---
# <a name="compiler-error-c3530"></a>Derleyici Hatası C3530

'auto' herhangi başka bir tür tanımlayıcısı ile birleştirilemez

Bir tür tanımlayıcısı ile kullanılan `auto` anahtar sözcüğü.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Bir tür belirleyiciye kullanan bir Değişken bildiriminde kullanmayın `auto` anahtar sözcüğü.

## <a name="example"></a>Örnek

Aşağıdaki örnek, çünkü C3530 verir değişkeni `x` ikisiyle bildirilen `auto` anahtar sözcüğü ile tür `int`, ve örnek ile derlenmiş **/Zc:auto**.

```
// C3530.cpp
// Compile with /Zc:auto
int main()
{
   auto int x;   // C3530
   return 0;
}
```

## <a name="see-also"></a>Ayrıca Bkz.

[auto Anahtar Sözcüğü](../../cpp/auto-keyword.md)