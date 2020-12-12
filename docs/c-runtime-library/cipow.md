---
description: 'Hakkında daha fazla bilgi edinin: _CIpow'
title: _CIpow
ms.date: 4/2/2020
api_name:
- _CIpow
- _o__CIpow
api_location:
- msvcr100.dll
- msvcr110.dll
- msvcr120.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr90.dll
- api-ms-win-crt-math-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- CIpow
- _CIpow
helpviewer_keywords:
- CIpow intrinsic
- _CIpow intrinsic
ms.assetid: 477aaf0c-ac58-4252-89dd-9f3e35d47536
ms.openlocfilehash: 69a51df94101091a59f188b1e39d62abb29de2b9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209639"
---
# <a name="_cipow"></a>_CIpow

*X* 'in, yığındaki en üstteki değerlere göre *y* kuvvetini hesaplar.

## <a name="syntax"></a>Syntax

```cpp
void __cdecl _CIpow();
```

## <a name="remarks"></a>Açıklamalar

İşlevin bu sürümünde `pow` derleyicinin anladığı özelleştirilmiş bir çağırma kuralı vardır. Kopyaların oluşturulmasını ve YAZMAÇ ayrılmasına yardımcı olmasını önlediği için yürütmeyi hızlandırır.

Elde edilen değer yığının en üstüne gönderilir.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](global-state.md).

## <a name="requirements"></a>Gereksinimler

**Platform:** x86

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[pow, powf, powl](../c-runtime-library/reference/pow-powf-powl.md)
