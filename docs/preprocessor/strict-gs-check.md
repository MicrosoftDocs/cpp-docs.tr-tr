---
description: 'Daha fazla bilgi edinin: strict_gs_check pragma'
title: strict_gs_check pragması
ms.date: 08/29/2019
f1_keywords:
- strict_gs_check
- strict_gs_check_CPP
helpviewer_keywords:
- strict_gs_check pragma
ms.assetid: decfec81-c916-42e0-a07f-8cc26df6a7ce
ms.openlocfilehash: 3fa1600bba59077ff66bfb0184bdd3ca4fe0e326
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197315"
---
# <a name="strict_gs_check-pragma"></a>strict_gs_check pragması

Bu pragma artırılmış güvenlik denetimi sağlar.

## <a name="syntax"></a>Syntax

> **#pragma strict_gs_check (** [ **push,** ] { **on**  |  **off** } **)**\
> **#pragma strict_gs_check (pop)**

## <a name="remarks"></a>Açıklamalar

Yığın tabanlı arabellek taşmasının bazı kategorilerini algılamaya yardımcı olması için, derleyiciye işlev yığınına rasgele bir tanımlama bilgisi eklemesini bildirir. Varsayılan olarak, `/GS` (arabellek güvenlik denetimi) derleyici seçeneği tüm işlevler için bir tanımlama bilgisi eklemez. Daha fazla bilgi için bkz. [/GS (arabellek güvenlik denetimi)](../build/reference/gs-buffer-security-check.md).

' İ `/GS` etkinleştirmek için kullanarak derleyin **strict_gs_check**.

Bu pragmayı, zarar verme olasılığı bulunan verilerin gördüğü kod modüllerinde kullanın. **strict_gs_check** agresif bir pragma ve bu savunmaya ihtiyaç duymayan işlevlere uygulanır, ancak sonuçta elde edilen uygulamanın performansına etkisini en aza indirmek için en iyi duruma getirilmiştir.

Bu pragmayı kullansanız bile, güvenli kod yazmak için çaba göstermelisiniz. Diğer bir deyişle, kodunuzun arabellek taşmalarına sahip olmadığından emin olun. **strict_gs_check** , uygulamanızı kodunuzda kalan arabellek taşlarından koruyabilir.

## <a name="example"></a>Örnek

Bu örnekte, bir diziyi yerel bir diziye kopyalayadığımızda bir arabellek taşması oluşur. Bu kodu ile derlerken `/GS` , dizi veri türü bir işaretçi olduğundan yığında hiçbir tanımlama bilgisi eklenmez. **Strict_gs_check** pragma eklemek, yığın tanımlama bilgisini işlev yığınına zorlar.

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

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)\
[/GS (Arabellek güvenlik denetimi)](../build/reference/gs-buffer-security-check.md)
