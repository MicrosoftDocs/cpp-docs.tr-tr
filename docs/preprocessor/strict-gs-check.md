---
title: strict_gs_check
ms.date: 11/04/2016
f1_keywords:
- strict_gs_check
- strict_gs_check_CPP
helpviewer_keywords:
- strict_gs_check pragma
ms.assetid: decfec81-c916-42e0-a07f-8cc26df6a7ce
ms.openlocfilehash: b62e1be466e65c0de6fb4eaa33ac6e99915529e6
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59037811"
---
# <a name="strictgscheck"></a>strict_gs_check

Bu pragma artırılmış güvenlik denetimi sağlar.

## <a name="syntax"></a>Sözdizimi

```
#pragma strict_gs_check([push,] on )
#pragma strict_gs_check([push,] off )
#pragma strict_gs_check(pop)
```

## <a name="remarks"></a>Açıklamalar

Yığın tabanlı arabellek taşmasının bazı kategorilerini algılamaya yardımcı olması için, derleyiciye işlev yığınına rasgele bir tanımlama bilgisi eklemesini bildirir. Varsayılan olarak, `/GS` (arabellek güvenlik denetimi) derleyici seçeneği tüm işlevler için bir tanımlama bilgisi eklenmez. Daha fazla bilgi için [/GS (arabellek güvenlik denetimi)](../build/reference/gs-buffer-security-check.md).

İle derleme `/GS` (arabellek güvenlik etkinleştirmek için işaretleyin) **strict_gs_check**.

Bu pragmayı, zarar verme olasılığı bulunan verilerin gördüğü kod modüllerinde kullanın. Bu pragma çok agresiftir ve bu savunmayı gerektirmeyen işlevlere uygulanır. Ancak sonuç uygulamasının performansı üzerindeki etkisini en aza indirmek için optimize edilmiştir.

Bu pragmayı kullansanız bile, güvenli kod yazmak için çaba göstermelisiniz. Diğer bir deyişle, kodunuzu hiçbir arabellek taşması olduğundan emin olun. **strict_gs_check** uygulama kodunuzda kalan arabellek taşmalarına korunmasına.

## <a name="example"></a>Örnek

Aşağıdaki kodda, bir diziyi yerel bir diziye kopyaladığımızda arabellek taşması oluşur. Bu kod ile derleme yaparken `/GS`, dizi veri türü bir işaretçi olduğu için yığına tanımlama bilgisi eklenir. Ekleme **strict_gs_check** pragması, yığın tanımlama bilgisini işlev yığınına zorlar.

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

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)<br/>
[/GS (Arabellek Güvenlik Denetimi)](../build/reference/gs-buffer-security-check.md)