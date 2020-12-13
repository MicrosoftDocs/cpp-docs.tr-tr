---
description: 'Daha fazla bilgi edinin: tamsayıların Indirgenmesi'
title: Tam Sayıların İndirgenmesi
ms.date: 11/04/2016
helpviewer_keywords:
- demoting integers
ms.assetid: 51fb3654-60b0-4de7-80eb-bd910086c18a
ms.openlocfilehash: d80adff34223d8aa785fa6ffa079a54af198a309
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186824"
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

[Tam Sayılar](../c-language/integers.md)
