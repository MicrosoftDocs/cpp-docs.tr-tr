---
description: pragmaMicrosoft C/C++ ' da strict_gs_check yönergesi hakkında daha fazla bilgi edinin
title: strict_gs_check pragma
ms.date: 01/22/2021
f1_keywords:
- strict_gs_check
- strict_gs_check_CPP
helpviewer_keywords:
- strict_gs_check pragma
- pragma, strict_gs_check
no-loc:
- pragma
ms.openlocfilehash: 4a224c42dc30227e5bd9a7142c807f7cebc34614
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713161"
---
# <a name="strict_gs_check-no-locpragma"></a>`strict_gs_check` pragma

Bu pragma , gelişmiş güvenlik denetimi sağlar.

## <a name="syntax"></a>Syntax

> **`#pragma strict_gs_check(`** [ **`push,`** ] { **`on`** | **`off`** } **`)`**\
> **`#pragma strict_gs_check( pop )`**

## <a name="remarks"></a>Açıklamalar

Yığın tabanlı arabellek taşmasının bazı kategorilerini algılamaya yardımcı olması için, derleyiciye işlev yığınına rasgele bir tanımlama bilgisi eklemesini bildirir. Varsayılan olarak, **`/GS`** derleyici seçeneği tüm işlevler için bir tanımlama bilgisi eklemez. Daha fazla bilgi için bkz. [ `/GS` (arabellek güvenlik denetimi)](../build/reference/gs-buffer-security-check.md).

Öğesini **`/GS`** etkinleştirmek için kullanarak derleyin **`strict_gs_check`** .

Bunu pragma , zararlı olabilecek verilere sunulan kod modüllerinde kullanın. **`strict_gs_check`** agresif bir pragma uygulamadır ve bu savunması gerekmeyen işlevlere uygulanır, ancak sonuçta elde edilen uygulamanın performansı üzerindeki etkisini en aza indirmek için en iyi duruma getirilmiştir.

Bunu kullansanız bile pragma , güvenli kod yazmak için çaba göstermelisiniz. Diğer bir deyişle, kodunuzun arabellek taşmalarına sahip olmadığından emin olun. **`strict_gs_check`** , kodunuzda kalan arabellek taşlarından uygulamanızı koruyabilir.

## <a name="example"></a>Örnek

Bu örnekte, bir diziyi yerel bir diziye kopyalayadığımızda bir arabellek taşması oluşur. Bu kodu ile derlerken **`/GS`** , dizi veri türü bir işaretçi olduğundan yığında hiçbir tanımlama bilgisi eklenmez. Öğesini eklemek, **`strict_gs_check`** pragma yığın tanımlama bilgisini işlev yığınına zorlar.

```cpp
// pragma_strict_gs_check.cpp
// compile with: /c

#pragma strict_gs_check(on)

void ** ReverseArray(void **pData,
                     size_t cData)
{
    // **_ This buffer is subject to being overrun!! _*_
    void _pReversed[20];

    // Reverse the array into a temporary buffer
    for (size_t j = 0, i = cData; i ; --i, ++j)
        // *** Possible buffer overrun!! ***
            pReversed[j] = pData[i];

    // Copy temporary buffer back into input/output buffer
    for (size_t i = 0; i < cData ; ++i)
        pData[i] = pReversed[i];

    return pData;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)\
[`/GS` (Arabellek güvenlik denetimi)](../build/reference/gs-buffer-security-check.md)
