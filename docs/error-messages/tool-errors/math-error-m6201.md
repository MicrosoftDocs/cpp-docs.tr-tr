---
title: Matematik hatası M6201 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- M6201
dev_langs:
- C++
helpviewer_keywords:
- M6201
ms.assetid: 4041c331-d9aa-4dd4-b565-7dbe0218538c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 87d2c09d6448bcf7fb0557fa3a174c60205a34ea
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099401"
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