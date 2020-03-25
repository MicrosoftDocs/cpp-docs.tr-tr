---
title: Matematik Hatası M6201
ms.date: 11/04/2016
f1_keywords:
- M6201
helpviewer_keywords:
- M6201
ms.assetid: 4041c331-d9aa-4dd4-b565-7dbe0218538c
ms.openlocfilehash: 0b1cd0d3fcd86a2174b19da41176dd97f547a295
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193712"
---
# <a name="math-error-m6201"></a>Matematik Hatası M6201

' function ': _DOMAIN hatası

Verilen işlevin bağımsız değişkeni, bu işlev için geçerli giriş değerlerinin etki alanının dışındaydı.

## <a name="example"></a>Örnek

```
result = sqrt(-1.0)   // C statement
result = SQRT(-1.0)   !  FORTRAN statement
```

Bu hata, işlev adı, bağımsız değişkenleri ve hata türü ile `_matherr` işlevini çağırır. Belirli çalışma zamanı kayan nokta matematik hatalarının işlenmesini özelleştirmek için `_matherr` işlevini yeniden yazabilirsiniz.
