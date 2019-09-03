---
title: __rdtsc
ms.date: 09/02/2019
f1_keywords:
- __rdtsc
helpviewer_keywords:
- __rdtsc intrinsic
- rdtsc instruction
- Read Time Stamp Counter instruction
ms.assetid: e31d0e51-c9bb-42ca-bbe9-a81ffe662387
ms.openlocfilehash: 837b68ca6ac63587cd43a7e8828777221c677e3c
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217142"
---
# <a name="__rdtsc"></a>__rdtsc

**Microsoft 'a özgü**

İşlemci zaman damgasını döndüren yönergeyiüretir.`rdtsc` İşlemci zaman damgası, son sıfırlamadan bu yana geçen saat döngüsü sayısını kaydeder.

## <a name="syntax"></a>Sözdizimi

```C
unsigned __int64 __rdtsc();
```

## <a name="return-value"></a>Dönüş değeri

Bir değer sayısını temsil eden 64 bitlik işaretsiz tamsayı.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__rdtsc`|x86, x64|

**Üst bilgi dosyası** \<Intrin. h >

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
