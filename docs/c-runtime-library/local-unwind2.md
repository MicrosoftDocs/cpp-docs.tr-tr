---
title: _local_unwind2
ms.date: 11/04/2016
apiname:
- _local_unwind2
apilocation:
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
- msvcr90.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- _local_unwind2
- local_unwind2
helpviewer_keywords:
- _local_unwind2 function
- local_unwind2 function
ms.assetid: 44f1fa82-e01e-490f-a6e6-18fc6811c28c
ms.openlocfilehash: c62763ecbdd2c05e8cd7b6733ec1df4254362527
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62342841"
---
# <a name="localunwind2"></a>_local_unwind2

İç CRT işlevi. Belirtilen kapsam tabloda listelenen tüm sonlandırma işleyicilerini çalıştırır.

## <a name="syntax"></a>Sözdizimi

```
void _local_unwind2(
   PEXCEPTION_REGISTRATION xr,
   int stop
);
```

#### <a name="parameters"></a>Parametreler

*XR*<br/>
[in] Bir kapsam tablo ile ilişkilendirilmiş bir kaydolma kaydı.

*Durdur*<br/>
[in] Yeri belirten sözcük düzeyi `_local_unwind2` durdurmanız gerekir.

## <a name="remarks"></a>Açıklamalar

Bu yöntem yalnızca çalışma zamanı ortamı tarafından kullanılır. Yöntemi, kodunuzda çağırmayın.

Sonlandırma işleyicileri bu yöntem yürütür, geçerli sözcük düzeyinde başlar ve works düzeyi, ulaşana kadar sözcük düzeylerinde yedekleme yolu tarafından belirtilen `stop`. Sonlandırma işleyicileri tarafından belirtilen düzeyde yürütmez `stop`.

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](../c-runtime-library/reference/crt-alphabetical-function-reference.md)
