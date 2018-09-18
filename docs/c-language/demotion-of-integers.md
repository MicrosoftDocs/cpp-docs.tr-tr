---
title: Tam sayıların indirgenmesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- demoting integers
ms.assetid: 51fb3654-60b0-4de7-80eb-bd910086c18a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 49177e7df11c0c7c4d7fefb201035ce12c5242af
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087532"
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