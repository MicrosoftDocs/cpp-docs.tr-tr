---
title: _CIsin
ms.date: 4/2/2020
api_name:
- _CIsin
- _o__CIsin
api_location:
- msvcr80.dll
- msvcr100.dll
- msvcrt.dll
- msvcr110.dll
- msvcr120.dll
- msvcr90.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-math-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- CIsin
- _CIsin
helpviewer_keywords:
- _CIsin intrinsic
- CIsin intrinsic
ms.assetid: f215f39a-2341-4f1c-ba8e-cb522451ceb2
ms.openlocfilehash: b7c3ba2c771d7659a7ca0ba2e64ade9068c2b390
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82917350"
---
# <a name="_cisin"></a>_CIsin

Kayan nokta yığınındaki en üstteki değerin sinüsünü hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
void __cdecl _CIsin();
```

## <a name="remarks"></a>Açıklamalar

[Sin](../c-runtime-library/reference/sin-sinf-sinl.md) işlevinin bu iç sürümünde derleyicinin anladığı özelleştirilmiş bir çağırma kuralı vardır. Kopyaların oluşturulmasını ve YAZMAÇ ayrılmasına yardımcı olmasını önlediği için yürütmeyi hızlandırır.

Elde edilen değer, kayan nokta yığınının en üstüne gönderilir.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](global-state.md).

## <a name="requirements"></a>Gereksinimler

**Platform:** x86

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[sin, sinf, sinl](../c-runtime-library/reference/sin-sinf-sinl.md)<br/>
