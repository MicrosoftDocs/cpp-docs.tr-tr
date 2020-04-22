---
title: _CIatan2
ms.date: 4/2/2020
api_name:
- _CIatan2
- _o__CIatan2
api_location:
- msvcr80.dll
- msvcrt.dll
- msvcr120.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr100.dll
- msvcr90.dll
- api-ms-win-crt-math-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- CIatan2
- _CIatan2
helpviewer_keywords:
- _CIatan2 intrinsic
- CIatan2 intrinsic
ms.assetid: 31f8cc78-b79f-4576-b73b-8add18e08680
ms.openlocfilehash: 585608b4d3dce723c0ea3a82e1c52325a0f6b7e6
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745923"
---
# <a name="_ciatan2"></a>_CIatan2

*X* ve *y'nin* yığının üstündeki değerlerin olduğu *x* / *y'nin* arctantını hesaplar.

## <a name="syntax"></a>Sözdizimi

```cpp
void __cdecl _CIatan2();
```

## <a name="remarks"></a>Açıklamalar

İşlevin `atan2` bu sürümüderleyicinin anladığı özel bir çağrı kuralına sahiptir. Kopyaların oluşturulmasını önlediği ve kayıt tahsisine yardımcı olduğu için yürütmeyi hızlandırıyor.

Elde edilen değer yığının üstüne itilir.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

**Platform:** x86

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[atan, atanf, atanl, atan2, atan2f, atan2l](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)
