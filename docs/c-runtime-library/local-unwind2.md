---
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
ms.openlocfilehash: cbcc0c6177ba4cc449daf6a385a7cce53b8c1230
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745334"
---
# <a name="_local_unwind2"></a>_local_unwind2

Dahili CRT fonksiyonu. Belirtilen kapsam tablosunda listelenen tüm sonlandırma işleyicilerini çalıştırın.

## <a name="syntax"></a>Sözdizimi

```cpp
void _local_unwind2(
   PEXCEPTION_REGISTRATION xr,
   int stop
);
```

#### <a name="parameters"></a>Parametreler

*Xr*<br/>
[içinde] Tek bir kapsam tablosuyla ilişkili bir kayıt kaydı.

*Durdurmak*<br/>
[içinde] Nerede `_local_unwind2` durması gerektiğini gösteren sözlü düzey.

## <a name="remarks"></a>Açıklamalar

Bu yöntem yalnızca çalışma zamanı ortamı tarafından kullanılır. Kodunuzdaki yöntemi aramayın.

Bu yöntem sonlandırma işleyicileri yürütür, geçerli sözlü düzeyde başlar ve tarafından `stop`belirtilen düzeye ulaşana kadar sözlük düzeylerde yolunda çalışır. Bu tarafından belirtilen düzeyde sonlandırma işleyicileri `stop`yürütmek değil.

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](../c-runtime-library/reference/crt-alphabetical-function-reference.md)
