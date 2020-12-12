---
description: 'Hakkında daha fazla bilgi edinin: _mm_stream_si64x'
title: _mm_stream_si64x
ms.date: 09/02/2019
f1_keywords:
- _mm_stream_si64x
helpviewer_keywords:
- movnti instruction
- _mm_stream_si64x intrinsic
ms.assetid: 114c2cd0-085f-41aa-846e-87bdd56c9ee7
ms.openlocfilehash: 2a68437905c0d5dd56a522d15985db7179921852
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97133230"
---
# <a name="_mm_stream_si64x"></a>_mm_stream_si64x

**Microsoft'a Özgü**

MOVNTı yönergesini üretir. Önbellekleri yoklamadan, *kaynaktaki* verileri *hedef* tarafından belirtilen bir bellek konumuna yazar.

## <a name="syntax"></a>Sözdizimi

```C
void _mm_stream_si64x(
   __int64 * Destination,
   __int64 Source
);
```

### <a name="parameters"></a>Parametreler

*Hedefine*\
dışı Kaynak verilerin yazılacağı konuma yönelik bir işaretçi.

*Kaynaktaki*\
'ndaki Yazılacak veriler.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`_mm_stream_si64x`|x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

Bu yordam yalnızca iç öğe olarak kullanılabilir.

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

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
