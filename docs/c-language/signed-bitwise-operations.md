---
description: 'Daha fazla bilgi edinin: Imzalı bit düzeyinde Işlemler'
title: İmzalı Bit Düzeyinde İşlemler
ms.date: 11/04/2016
helpviewer_keywords:
- bitwise operations
- signed bitwise operations
ms.assetid: 1e5cf65b-ee32-41a0-a5c2-82c1854091f6
ms.openlocfilehash: 98cca4d7450e0b65301ba3d2ad65f0cb3aca81ea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97292656"
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
