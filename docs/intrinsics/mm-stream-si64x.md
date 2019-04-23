---
title: _mm_stream_si64x
ms.date: 11/04/2016
f1_keywords:
- _mm_stream_si64x
helpviewer_keywords:
- movnti instruction
- _mm_stream_si64x intrinsic
ms.assetid: 114c2cd0-085f-41aa-846e-87bdd56c9ee7
ms.openlocfilehash: d7f7a75be1602fbb70a230b0dd3a791be99d092a
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59039604"
---
# <a name="mmstreamsi64x"></a>_mm_stream_si64x

**Microsoft'a özgü**

MOVNTI yönerge oluşturur. Verileri Yazar `Source` tarafından belirtilen bellek konumuna `Dest`, önbellekler kirletmesini olmadan.

## <a name="syntax"></a>Sözdizimi

```
void _mm_stream_si64x(
   __int64 * Dest,
   __int64 Source
);
```

#### <a name="parameters"></a>Parametreler

*Hedef*<br/>
[out] Kaynak veri yazmak için konumu için bir işaretçi.

*Kaynak*<br/>
[in] Yazılacak veriler.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`_mm_stream_si64x`|X64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

Bu yordam yalnızca bir iç öğe olarak kullanılabilir.

## <a name="example"></a>Örnek

```C
// _mm_stream_si64x.c
// processor: x64

#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(_mm_stream_si64x)

int main()
{
    __int64 val = 0xFFFFFFFFFFFFI64;
    __int64 a[10];

    memset(a, 0, sizeof(a));
    _mm_stream_si64x(a+1, val);
    printf_s( "%I64x %I64x %I64x %I64x", a[0], a[1], a[2], a[3]);
}
```

```Output
0 ffffffffffff 0 0
```

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)