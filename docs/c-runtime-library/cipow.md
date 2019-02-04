---
title: _CIpow
ms.date: 11/04/2016
apiname:
- _CIpow
apilocation:
- msvcr100.dll
- msvcr110.dll
- msvcr120.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr90.dll
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- CIpow
- _CIpow
helpviewer_keywords:
- CIpow intrinsic
- _CIpow intrinsic
ms.assetid: 477aaf0c-ac58-4252-89dd-9f3e35d47536
ms.openlocfilehash: 2fa3fd415ac76f42e4c01153783d0d1e3adb586a
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55703252"
---
# <a name="cipow"></a>_CIpow

Hesaplar *x* için harekete geçirilen *y* power temel yığınında üst alan.

## <a name="syntax"></a>Sözdizimi

```
void __cdecl _CIpow();
```

## <a name="remarks"></a>Açıklamalar

Bu sürümü `pow` derleyici anlayan özelleştirilmiş bir çağırma kuralı işlevi vardır. Kopya oluşturulmasını önlediği için yürütmeyi hızlandırır ve YAZMAÇ ayırma ile yardımcı olur.

Sonuç değerini yığın üstüne itilir.

## <a name="requirements"></a>Gereksinimler

**Platform:** x86

## <a name="see-also"></a>Ayrıca Bkz.

[Alfabetik İşlev Başvurusu](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[pow, powf, powl](../c-runtime-library/reference/pow-powf-powl.md)