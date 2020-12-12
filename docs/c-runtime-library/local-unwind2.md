---
description: 'Hakkında daha fazla bilgi edinin: _local_unwind2'
title: _local_unwind2
ms.date: 11/04/2016
api_name:
- _local_unwind2
api_location:
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
- msvcr90.dll
- msvcr120.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _local_unwind2
- local_unwind2
helpviewer_keywords:
- _local_unwind2 function
- local_unwind2 function
ms.assetid: 44f1fa82-e01e-490f-a6e6-18fc6811c28c
ms.openlocfilehash: b2e3ca2f792abaa3ace54b25131d82c21aadf972
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97246415"
---
# <a name="_local_unwind2"></a>_local_unwind2

İç CRT Işlevi. Belirtilen kapsam tablosunda listelenen tüm sonlandırma işleyicilerini çalıştırır.

## <a name="syntax"></a>Sözdizimi

```cpp
void _local_unwind2(
   PEXCEPTION_REGISTRATION xr,
   int stop
);
```

#### <a name="parameters"></a>Parametreler

*XR*<br/>
'ndaki Bir kapsam tablosuyla ilişkili bir kayıt kaydı.

*durdurulması*<br/>
'ndaki Nerede durması gerektiğini gösteren sözlü düzeyi `_local_unwind2` .

## <a name="remarks"></a>Açıklamalar

Bu yöntem yalnızca çalışma zamanı ortamı tarafından kullanılır. Kodunuzda yöntemini çağırmayın.

Bu yöntem sonlandırma işleyicilerini yürüttüğünde, bu, geçerli sözcük düzeyinde başlar ve tarafından belirtilen düzeye ulaşana kadar alt düzey düzeylerde çalışır `stop` . Sonlandırma işleyicilerini tarafından belirtilen düzeyde yürütmez `stop` .

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](../c-runtime-library/reference/crt-alphabetical-function-reference.md)
