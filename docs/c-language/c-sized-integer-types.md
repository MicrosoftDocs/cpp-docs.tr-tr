---
title: C Boyutlu Tamsayı Türleri
ms.date: 11/04/2016
helpviewer_keywords:
- sized integer types
ms.assetid: 0d6199b4-d0ab-4e8c-a769-785f5afb92eb
ms.openlocfilehash: 136065466d3adb4017cf18f2baf8c3387ffbd035
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62313304"
---
# <a name="c-sized-integer-types"></a>C Boyutlu Tamsayı Türleri

**Microsoft'a Özgü**

Microsoft C, boyutlandırılmış tamsayı türleri için destek sağlar. __İnt*n* tür tanımlayıcısını kullanarak 8, 16-, 32-veya 64-bit tamsayı değişkenleri bildirebilirsiniz; burada *n* , tamsayı değişkeninin bit cinsinden boyutudur. *N* değeri 8, 16, 32 veya 64 olabilir. Aşağıdaki örnekte, boyutlandırılmış tamsayıların dört türünün her biri için bir değişken bildirilmektedir:

```
__int8 nSmall;      // Declares 8-bit integer
__int16 nMedium;    // Declares 16-bit integer
__int32 nLarge;     // Declares 32-bit integer
__int64 nHuge;      // Declares 64-bit integer
```

Boyutlandırılmış tamsayıların ilk üç türü, aynı boyuta sahip ANSI türleri için eş anlamlıdır ve birden fazla platformda aynı şekilde davranan taşınabilir kod yazmak için yararlıdır. __İnt8 veri türünün char türü ile eşanlamlı olduğunu, \__int16 tür Short ile eşanlamlı olduğunu ve \__int32 ise int türünde eş anlamlı olduğunu unutmayın. \__İnt64 türünün EŞDEĞERI bir ANSI karşılığı yok.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Temel türlerin depolanması](../c-language/storage-of-basic-types.md)
