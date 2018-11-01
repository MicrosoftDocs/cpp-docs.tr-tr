---
title: Matematik Hatası M6201
ms.date: 11/04/2016
f1_keywords:
- M6201
helpviewer_keywords:
- M6201
ms.assetid: 4041c331-d9aa-4dd4-b565-7dbe0218538c
ms.openlocfilehash: 6d3f107de7e45653374036ecafaa864cb3eff5b0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622111"
---
# <a name="math-error-m6201"></a>Matematik Hatası M6201

'function': _etki alanı hatası

Verilen işlevin bağımsız değişkeni geçerli bir giriş değerleri söz konusu işlev için etki alanı dışındaki oluştu.

## <a name="example"></a>Örnek

```
result = sqrt(-1.0)   // C statement
result = SQRT(-1.0)   !  FORTRAN statement
```

Bu hata çağırır `_matherr` işlevi işlev adı, bağımsız ve hata türü. Yeniden yazabilirsiniz `_matherr` belirli çalışma zamanı kayan nokta matematik hataları işleme özelleştirmek için işlevi.