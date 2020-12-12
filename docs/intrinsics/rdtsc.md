---
description: 'Hakkında daha fazla bilgi edinin: __rdtsc'
title: __rdtsc
ms.date: 09/02/2019
f1_keywords:
- __rdtsc
helpviewer_keywords:
- __rdtsc intrinsic
- rdtsc instruction
- Read Time Stamp Counter instruction
ms.assetid: e31d0e51-c9bb-42ca-bbe9-a81ffe662387
ms.openlocfilehash: 930c8fbd0ae762c8674a85e379899bc4fe4d3394
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257517"
---
# <a name="__rdtsc"></a>__rdtsc

**Microsoft'a Özgü**

`rdtsc`İşlemci zaman damgasını döndüren yönergeyi üretir. İşlemci zaman damgası, son sıfırlamadan bu yana geçen saat döngüsü sayısını kaydeder.

## <a name="syntax"></a>Sözdizimi

```C
unsigned __int64 __rdtsc();
```

## <a name="return-value"></a>Döndürülen değer

Bir değer sayısını temsil eden 64 bitlik işaretsiz tamsayı.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__rdtsc`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

Bu yordam yalnızca bir iç öğe olarak kullanılabilir.

Daha sonraki nesil donanımlar içindeki TSC değerinin yorumu, önceki x64 sürümlerindeki sürümünden farklıdır. Daha fazla bilgi için bkz. donanım el kitabı.

## <a name="example"></a>Örnek

```cpp
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

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
