---
title: Tam Sayıların İndirgenmesi
ms.date: 11/04/2016
helpviewer_keywords:
- demoting integers
ms.assetid: 51fb3654-60b0-4de7-80eb-bd910086c18a
ms.openlocfilehash: 5dca8d414e7cf7dd04d405208ad6a86dd4372542
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50480918"
---
# <a name="demotion-of-integers"></a>Tam Sayıların İndirgenmesi

**ANSI 3.2.1.2** değer gösterilemiyorsa bir işaretsiz tamsayı eşit uzunluktaki bir işaretli tamsayıya dönüştürme sonucunu veya bir tamsayı daha kısa işaretli tamsayıya dönüştürülmesinin sonucu

Olduğunda bir **uzun** tamsayı türünden **kısa**, veya bir **kısa** türüne dönüştürülür bir `char`, az öneme sahip baytlar korunur.

Örneğin, bu satır

```
short x = (short)0x12345678L;
```

0x5678 değerini `x`'e atar ve bu satır

```
char y = (char)0x1234;
```

0x34 değerini `y`'ye atar.

İşaretli değişkenler işaretsiz değişkenlere ve işaretsiz değişkenler işaretli değişkenlere dönüştürüldüğünde, bit düzenleri aynı kalır. Örneğin, -2 atama (0xFE) işaretsiz bir değere 254 (aynı zamanda 0xFE) verir.

## <a name="see-also"></a>Ayrıca Bkz.

[Tam Sayılar](../c-language/integers.md)