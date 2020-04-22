---
title: _CIsqrt
ms.date: 4/2/2020
api_name:
- _CIsqrt
- _o__CIsqrt
api_location:
- msvcr90.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcrt.dll
- msvcr110.dll
- msvcr100.dll
- api-ms-win-crt-math-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _CIsqrt
- CIsqrt
helpviewer_keywords:
- CIsqrt intrinsic
- _CIsqrt intrinsic
ms.assetid: 663548ea-398c-48ee-8397-a787c6ebb937
ms.openlocfilehash: e6bed6dcde8f4f80e323da120ddb3f2488f769a1
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745424"
---
# <a name="_cisqrt"></a>_CIsqrt

Yığındaki en üst değerin kare kökünü hesaplar.

## <a name="syntax"></a>Sözdizimi

```cpp
void __cdecl _CIsqrt();
```

## <a name="remarks"></a>Açıklamalar

İşlevin `sqrt` bu sürümüderleyicinin anladığı özel bir çağrı kuralına sahiptir. Kopyaların oluşturulmasını önlediği ve kayıt tahsisine yardımcı olduğu için yürütmeyi hızlandırıyor.

Elde edilen değer yığının üstüne itilir.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

**Platform:** x86

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[sqrt, sqrtf, sqrtl](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)
