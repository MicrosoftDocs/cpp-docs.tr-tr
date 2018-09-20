---
title: __rdtsc | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __rdtsc
dev_langs:
- C++
helpviewer_keywords:
- __rdtsc intrinsic
- rdtsc instruction
- Read Time Stamp Counter instruction
ms.assetid: e31d0e51-c9bb-42ca-bbe9-a81ffe662387
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d10bf2392d7e469f8f9a8a113b96e0cf2be88a50
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46434537"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)