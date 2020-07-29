---
title: Tam Sayıların İndirgenmesi
ms.date: 11/04/2016
helpviewer_keywords:
- demoting integers
ms.assetid: 51fb3654-60b0-4de7-80eb-bd910086c18a
ms.openlocfilehash: aee0a5041cd37b1fbad785b760b8cefde74eb195
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218890"
---
# <a name="demotion-of-integers"></a>Tam Sayıların İndirgenmesi

**ANSI 3.2.1.2** Bir tamsayıyı daha kısa işaretli bir tamsayıya dönüştürmenin sonucu veya işaretsiz bir tamsayıyı, değer temsil edilene eşit uzunlukta işaretli bir tamsayıya dönüştürme sonucu

Bir **`long`** tamsayı bir öğesine veya ' a atama yapıldığında, **`short`** **`short`** **`char`** en az önemli baytlar korunur.

Örneğin, bu satır

```
short x = (short)0x12345678L;
```

0x5678 değerini `x`'e atar ve bu satır

```
char y = (char)0x1234;
```

0x34 değerini `y`'ye atar.

**`signed`** Değişkenler öğesine dönüştürülüp tersi durumda **`unsigned`** , bit desenleri de aynı kalır. Örneğin, bir değere atama-2 (0xFE) **`unsigned`** 254 (Ayrıca 0xFE) verir.

## <a name="see-also"></a>Ayrıca bkz.

[Kesirli](../c-language/integers.md)
