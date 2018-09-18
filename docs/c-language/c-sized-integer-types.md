---
title: C boyutlu tamsayı türleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- sized integer types
ms.assetid: 0d6199b4-d0ab-4e8c-a769-785f5afb92eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 037ff61dbe1d1d42d8b0c751fcdc83f01a8dd112
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46101429"
---
# <a name="c-sized-integer-types"></a>C Boyutlu Tamsayı Türleri

**Microsoft'a özgü**

Microsoft C, boyutlandırılmış tamsayı türleri için destek sağlar. __İnt kullanarak 8, 16, 32 veya 64-bit tamsayı değişkenleri bildirebilirsiniz*n* tür tanımlayıcısı, burada *n* tamsayı değişkeninin bit olarak boyutudur. Değerini *n* 8, 16, 32 veya 64 olabilir. Aşağıdaki örnekte, boyutlandırılmış tamsayıların dört türünün her biri için bir değişken bildirilmektedir:

```
__int8 nSmall;      // Declares 8-bit integer
__int16 nMedium;    // Declares 16-bit integer
__int32 nLarge;     // Declares 32-bit integer
__int64 nHuge;      // Declares 64-bit integer
```

Boyutlandırılmış tamsayıların ilk üç türü, aynı boyuta sahip ANSI türleri için eş anlamlıdır ve birden fazla platformda aynı şekilde davranan taşınabilir kod yazmak için yararlıdır. __İnt8 veri türünün char türü ile eş anlamlı olduğuna dikkat edin \__int16 türünün short, ve \__int32 Tamsayı türünde ile eşanlamlı \__İnt64 türünde hiçbir eşdeğer ANSI karşılığı.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Temel Türleri Depolama](../c-language/storage-of-basic-types.md)