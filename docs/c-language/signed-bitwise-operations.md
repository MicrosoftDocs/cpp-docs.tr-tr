---
title: İmzalı Bit Düzeyinde İşlemler
ms.date: 11/04/2016
helpviewer_keywords:
- bitwise operations
- signed bitwise operations
ms.assetid: 1e5cf65b-ee32-41a0-a5c2-82c1854091f6
ms.openlocfilehash: 43f65fd5d1ea14ef5e15f18d9c8516ccf5fb1e08
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62158325"
---
# <a name="signed-bitwise-operations"></a>İmzalı Bit Düzeyinde İşlemler

**Ansı 3,3** İşaretli tamsayılar üzerinde bit düzeyinde işlemlerin sonuçları

İşaretli tamsayılarda bit düzeyinde işlemler, işaretsiz tamsayılarda bit düzeyinde işlemlerle aynı şekilde çalışır. Örneğin, `-16 & 99` ikili dosyada şu şekilde ifade edilebilir

```
  11111111 11110000
& 00000000 01100011
  _________________
  00000000 01100000
```

Bit düzeyinde AND'in sonucu 96'dır.

## <a name="see-also"></a>Ayrıca bkz.

[Tam Sayılar](../c-language/integers.md)
