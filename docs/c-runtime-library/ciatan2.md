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
ms.openlocfilehash: 2535cb5747b5eac9257594bd4c6d91e64ee7b3eb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81334395"
---
# <a name="_ciatan2"></a>_CIatan2

*X* ve *y'nin* yığının üstündeki değerlerin olduğu *x* / *y'nin* arctantını hesaplar.

## <a name="syntax"></a>Sözdizimi

```
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
