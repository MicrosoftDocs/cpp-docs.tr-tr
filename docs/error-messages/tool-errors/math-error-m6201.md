---
description: 'Daha fazla bilgi edinin: matematik hatası M6201'
title: Matematik Hatası M6201
ms.date: 11/04/2016
f1_keywords:
- M6201
helpviewer_keywords:
- M6201
ms.assetid: 4041c331-d9aa-4dd4-b565-7dbe0218538c
ms.openlocfilehash: 03588b7eed580b95cb263f6e4d71f5a793f4d392
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244322"
---
# <a name="math-error-m6201"></a>Matematik Hatası M6201

' function ': _DOMAIN hatası

Verilen işlevin bağımsız değişkeni, bu işlev için geçerli giriş değerlerinin etki alanının dışındaydı.

## <a name="example"></a>Örnek

```
result = sqrt(-1.0)   // C statement
result = SQRT(-1.0)   !  FORTRAN statement
```

Bu hata işlev `_matherr` adı, bağımsız değişkenleri ve hata türü ile işlevi çağırır. `_matherr`Belirli çalışma zamanı kayan nokta matematik hatalarının işlenmesini özelleştirmek için işlevi yeniden yazabilirsiniz.
