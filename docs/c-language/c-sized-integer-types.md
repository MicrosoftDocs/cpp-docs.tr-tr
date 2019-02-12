---
title: C Boyutlu Tamsayı Türleri
ms.date: 11/04/2016
helpviewer_keywords:
- sized integer types
ms.assetid: 0d6199b4-d0ab-4e8c-a769-785f5afb92eb
ms.openlocfilehash: 136065466d3adb4017cf18f2baf8c3387ffbd035
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56150694"
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

## <a name="see-also"></a>Ayrıca bkz.

[Temel Türleri Depolama](../c-language/storage-of-basic-types.md)
