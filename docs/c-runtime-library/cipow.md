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
ms.openlocfilehash: c09801841e25b5de2f98e64c01bf48b1eea9992b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46052094"
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