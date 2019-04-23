---
title: __rdtsc
ms.date: 11/04/2016
f1_keywords:
- __rdtsc
helpviewer_keywords:
- __rdtsc intrinsic
- rdtsc instruction
- Read Time Stamp Counter instruction
ms.assetid: e31d0e51-c9bb-42ca-bbe9-a81ffe662387
ms.openlocfilehash: 6f30be3340ae1be237bb2f8a008a8cb60c7351f0
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59036844"
---
# <a name="rdtsc"></a>__rdtsc

**Microsoft'a özgü**

Oluşturur `rdtsc` form veya yönerge işlemcisi zaman damgasını döndürür. İşlemci zaman damgası, son sıfırlamadan sonraki saat döngüsü sayısını kaydeder.

## <a name="syntax"></a>Sözdizimi

```
unsigned __int64 __rdtsc();
```

## <a name="return-value"></a>Dönüş Değeri

İşaret sayısını temsil eden bir 64-bit işaretsiz tamsayı.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__rdtsc`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

Bu yordam yalnızca bir iç öğe kullanılabilir.

Bu nesil donanım TSC değerin yorumu, x64 önceki sürümlerinde farklılık gösterir. Daha fazla bilgi için donanım kılavuzlarına bakın.

## <a name="example"></a>Örnek

```
// rdtsc.cpp
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__rdtsc)

int main()
{
    unsigned __int64 i;
    i = __rdtsc();
    printf_s("%I64d ticks\n", i);
}
```

```Output
3363423610155519 ticks
```

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)