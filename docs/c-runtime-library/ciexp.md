---
title: _CIexp
ms.date: 4/2/2020
api_name:
- _CIexp
- _o__CIexp
api_location:
- msvcr120.dll
- msvcr80.dll
- msvcr110.dll
- msvcr100.dll
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- api-ms-win-crt-math-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- CIexp
- _CIexp
helpviewer_keywords:
- CIexp intrinsic
- _CIexp intrinsic
ms.assetid: f8a3e3b7-fa57-41a3-9983-6c81914cbb55
ms.openlocfilehash: 90a8fdac4b3b671853d2274de26040e3bf67def4
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82918040"
---
# <a name="_ciexp"></a>_CIexp

Yığındaki en üstteki değerin üstel değerini hesaplar.

## <a name="syntax"></a>Sözdizimi

```cpp
void __cdecl _CIexp();
```

## <a name="remarks"></a>Açıklamalar

`exp` İşlevin bu sürümünde derleyicinin anladığı özelleştirilmiş bir çağırma kuralı vardır. Kopyaların oluşturulmasını ve YAZMAÇ ayrılmasına yardımcı olmasını önlediği için yürütmeyi hızlandırır.

Elde edilen değer yığının en üstüne gönderilir.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](global-state.md).

## <a name="requirements"></a>Gereksinimler

**Platform:** x86

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[exp, expf, expl](../c-runtime-library/reference/exp-expf.md)
