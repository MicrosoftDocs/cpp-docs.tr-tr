---
title: _Cısqrt | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _CIsqrt
apilocation:
- msvcr90.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcrt.dll
- msvcr110.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- _CIsqrt
- CIsqrt
dev_langs:
- C++
helpviewer_keywords:
- CIsqrt intrinsic
- _CIsqrt intrinsic
ms.assetid: 663548ea-398c-48ee-8397-a787c6ebb937
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 04c628dec2c2fd7e0b0b5a61aa20abf9266ca416
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46084451"
---
# <a name="cisqrt"></a>_CIsqrt

Yığındaki en üst değer karekökünü hesaplar.

## <a name="syntax"></a>Sözdizimi

```
void __cdecl _CIsqrt();
```

## <a name="remarks"></a>Açıklamalar

Bu sürümü `sqrt` derleyici anlayan özelleştirilmiş bir çağırma kuralı işlevi vardır. Kopya oluşturulmasını önlediği için yürütmeyi hızlandırır ve YAZMAÇ ayırma ile yardımcı olur.

Sonuç değerini yığın üstüne itilir.

## <a name="requirements"></a>Gereksinimler
 **Platform:** x86

## <a name="see-also"></a>Ayrıca Bkz.

[Alfabetik İşlev Başvurusu](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[sqrt, sqrtf, sqrtl](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)