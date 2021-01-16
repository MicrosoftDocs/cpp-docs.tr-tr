---
description: 'Hakkında daha fazla bilgi edinin: _local_unwind2'
title: _local_unwind2
ms.date: 1/14/2021
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: cb137547c44eb6d6516086a06109a9339247699c
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2021
ms.locfileid: "98243066"
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
