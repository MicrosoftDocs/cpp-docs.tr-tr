---
title: _CItan
ms.date: 4/2/2020
api_name:
- _CItan
- _o__CItan
api_location:
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr80.dll
- msvcrt.dll
- msvcr110.dll
- msvcr90.dll
- msvcr120.dll
- api-ms-win-crt-math-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _CItan
- CItan
helpviewer_keywords:
- CItan intrinsic
- _CItan intrinsic
ms.assetid: d1ea3113-50a2-45a6-b6bc-680fcdcc0928
ms.openlocfilehash: 8c6cc0a51d6ef2132172164306b84f73799da729
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81349360"
---
# <a name="_citan"></a>_CItan

Kayan nokta yığınındaki en üst değerin teğetini hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
void __cdecl _CItan();
```

## <a name="remarks"></a>Açıklamalar

[Tan](../c-runtime-library/reference/tan-tanf-tanl.md) işlevinin bu sürümü derleyicinin anladığı özel bir çağrı kuralına sahiptir. İşlev yürütmeyi hızlandırıyor, çünkü kopyaların oluşturulmasını engeller ve kayıt tahsisine yardımcı olur.

Elde edilen değer kayan nokta yığınının üstüne itilir.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

**Platform:** x86

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[tan, tanf, tanl](../c-runtime-library/reference/tan-tanf-tanl.md)<br/>
