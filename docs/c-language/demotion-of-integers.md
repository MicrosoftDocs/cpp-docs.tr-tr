---
title: Tam Sayıların İndirgenmesi
ms.date: 11/04/2016
helpviewer_keywords:
- demoting integers
ms.assetid: 51fb3654-60b0-4de7-80eb-bd910086c18a
ms.openlocfilehash: edfb8f03094c10cf0cf33b0eb799d5d822ac017d
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56152657"
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

## <a name="see-also"></a>Ayrıca bkz.

[Tam Sayılar](../c-language/integers.md)
