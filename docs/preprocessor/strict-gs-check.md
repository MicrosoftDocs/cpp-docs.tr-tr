---
title: strict_gs_check pragması
ms.date: 08/29/2019
f1_keywords:
- strict_gs_check
- strict_gs_check_CPP
helpviewer_keywords:
- strict_gs_check pragma
ms.assetid: decfec81-c916-42e0-a07f-8cc26df6a7ce
ms.openlocfilehash: 0b66e87f2280c923d05103fccfcbbc8d32daf3fd
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216589"
---
# <a name="strict_gs_check-pragma"></a>strict_gs_check pragması

Bu pragma artırılmış güvenlik denetimi sağlar.

## <a name="syntax"></a>Sözdizimi

> **#pragma strict_gs_check (** [ **push,** ] { **on** | **off** } **)** \
> **#pragma strict_gs_check (pop)**

## <a name="remarks"></a>Açıklamalar

Yığın tabanlı arabellek taşmasının bazı kategorilerini algılamaya yardımcı olması için, derleyiciye işlev yığınına rasgele bir tanımlama bilgisi eklemesini bildirir. Varsayılan olarak, `/GS` (arabellek güvenlik denetimi) derleyici seçeneği tüm işlevler için bir tanımlama bilgisi eklemez. Daha fazla bilgi için bkz. [/GS (arabellek güvenlik denetimi)](../build/reference/gs-buffer-security-check.md).

Strict_gs_check 'i etkinleştirmek `/GS` için kullanarakderleyin.

Bu pragmayı, zarar verme olasılığı bulunan verilerin gördüğü kod modüllerinde kullanın. **strict_gs_check** , agresif bir pragma ve bu savunmaya ihtiyaç duymayan işlevlere uygulanır, ancak sonuçta elde edilen uygulamanın performansına etkisini en aza indirmek için en iyi duruma getirilmiştir.

Bu pragmayı kullansanız bile, güvenli kod yazmak için çaba göstermelisiniz. Diğer bir deyişle, kodunuzun arabellek taşmalarına sahip olmadığından emin olun. **strict_gs_check** , uygulamanızı kodunuzda kalan arabellek taşlarından koruyabilir.

## <a name="example"></a>Örnek

Bu örnekte, bir diziyi yerel bir diziye kopyalayadığımızda bir arabellek taşması oluşur. Bu kodu ile `/GS`derlerken, dizi veri türü bir işaretçi olduğundan yığında hiçbir tanımlama bilgisi eklenmez. **Strict_gs_check** pragma eklemek, yığın tanımlama bilgisini işlev yığınına zorlar.

```cpp
// pragma_strict_gs_check.cpp
// compile with: /c

#pragma strict_gs_check(on)

void ** ReverseArray(void **pData,
                     size_t cData)
{
    // *** This buffer is subject to being overrun!! ***
    void *pReversed[20];

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
[/GS (arabellek güvenlik denetimi)](../build/reference/gs-buffer-security-check.md)
