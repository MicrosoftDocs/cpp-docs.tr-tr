---
title: _Cıpow | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
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
apitype: DLLExport
f1_keywords:
- CIpow
- _CIpow
dev_langs:
- C++
helpviewer_keywords:
- CIpow intrinsic
- _CIpow intrinsic
ms.assetid: 477aaf0c-ac58-4252-89dd-9f3e35d47536
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 01fa112fe70094cbf97537e6288751ac14acd2db
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48235959"
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