---
title: İmzalı Bit Düzeyinde İşlemler
ms.date: 11/04/2016
helpviewer_keywords:
- bitwise operations
- signed bitwise operations
ms.assetid: 1e5cf65b-ee32-41a0-a5c2-82c1854091f6
ms.openlocfilehash: d178900a25a5d7a080068fb1919fcba2853bef14
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50652016"
---
# <a name="signed-bitwise-operations"></a>İmzalı Bit Düzeyinde İşlemler

**ANSI 3.3** işaretli tamsayılarda bit düzeyinde sonuçları

İşaretli tamsayılarda bit düzeyinde işlemler, işaretsiz tamsayılarda bit düzeyinde işlemlerle aynı şekilde çalışır. Örneğin, `-16 & 99` ikili olarak ifade edilebilir

```
  11111111 11110000
& 00000000 01100011
  _________________
  00000000 01100000
```

Bit düzeyinde AND'in sonucu 96'dır.

## <a name="see-also"></a>Ayrıca Bkz.

[Tam Sayılar](../c-language/integers.md)