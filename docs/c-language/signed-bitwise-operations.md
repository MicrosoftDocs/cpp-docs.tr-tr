---
title: İmzalı bit düzeyinde işlemler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- bitwise operations
- signed bitwise operations
ms.assetid: 1e5cf65b-ee32-41a0-a5c2-82c1854091f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 184fd5a0e6c12cb58e9fed759459e7b8172896f8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46038303"
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