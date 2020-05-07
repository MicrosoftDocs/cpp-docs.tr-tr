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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 65cce8b094a1508566e2de7162b9e8e76712742a
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82918327"
---
# <a name="_citan"></a>_CItan

Kayan nokta yığınındaki en üstteki değerin tanjantını hesaplar.

## <a name="syntax"></a>Sözdizimi

```C
void __cdecl _CItan();
```

## <a name="remarks"></a>Açıklamalar

[Tan](../c-runtime-library/reference/tan-tanf-tanl.md) işlevinin bu sürümünde derleyicinin anladığı özelleştirilmiş bir çağırma kuralı vardır. İşlev, kopyaların oluşturulmasını ve YAZMAÇ ayrılmasına yardımcı olmaya engel olduğundan yürütmeyi hızlandırır.

Elde edilen değer, kayan nokta yığınının en üstüne gönderilir.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](global-state.md).

## <a name="requirements"></a>Gereksinimler

**Platform:** x86

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[tan, tanf, tanl](../c-runtime-library/reference/tan-tanf-tanl.md)<br/>
