---
description: 'Daha fazla bilgi edinin: C boyutlu tamsayı türleri'
title: C Boyutlu Tamsayı Türleri
ms.date: 07/22/2020
helpviewer_keywords:
- sized integer types
ms.assetid: 0d6199b4-d0ab-4e8c-a769-785f5afb92eb
ms.openlocfilehash: ad50806f52638884da69e109da252379dea0d571
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300131"
---
# <a name="c-sized-integer-types"></a>C Boyutlu Tamsayı Türleri

**Microsoft'a Özgü**

Microsoft C, boyutlandırılmış tamsayı türleri için destek sağlar. Tür belirticisini kullanarak 8, 16, 32-veya 64-bit tamsayı değişkenleri `__intN` , burada *`N`* tamsayı değişkeninin bit cinsinden boyutudur. *N* değeri 8, 16, 32 veya 64 olabilir. Aşağıdaki örnekte, boyutlandırılmış tamsayıların dört türünün her biri için bir değişken bildirilmektedir:

```C
__int8  nSmall;     // Declares 8-bit integer
__int16 nMedium;    // Declares 16-bit integer
__int32 nLarge;     // Declares 32-bit integer
__int64 nHuge;      // Declares 64-bit integer
```

Boyutlandırılmış tamsayıların ilk üç türü, aynı boyutta olan ANSI türleri için eş anlamlılardır. Birden çok platformda aynı şekilde davranan taşınabilir kod yazmak için faydalıdır. **`__int8`** Veri türü türü ile eşanlamlıdır, türü ile eşanlamlıdır, türü ile eşanlamlıdır **`char`** **`__int16`** **`short`** **`__int32`** **`int`** ve **`__int64`** türüyle **`long long`** eşanlamlı olur.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Temel türlerin depolanması](../c-language/storage-of-basic-types.md)
