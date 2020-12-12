---
description: 'Hakkında daha fazla bilgi edinin: __mulh'
title: __mulh
ms.date: 09/02/2019
f1_keywords:
- __mulh
helpviewer_keywords:
- __mulh intrinsic
ms.assetid: cd2ab093-9ef6-404d-ac34-0bee033882f3
ms.openlocfilehash: 0cee31b6a9e1088d76200cd46482fd4aaf80474b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118946"
---
# <a name="__mulh"></a>__mulh

**Microsoft'a Özgü**

2 64 bit işaretli tamsayılar ürününün yüksek 64 bitini döndürür.

## <a name="syntax"></a>Sözdizimi

```C
__int64 __mulh(
   __int64 a,
   __int64 b
);
```

### <a name="parameters"></a>Parametreler

*a*\
'ndaki Çarpılacak ilk sayı.

*kenarı*\
'ndaki Çarpılacak ikinci sayı.

## <a name="return-value"></a>Döndürülen değer

Çarpma 'nın 128 bit sonucunun yüksek 64 bitleri.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__mulh`|x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

Bu yordam yalnızca iç öğe olarak kullanılabilir.

## <a name="example"></a>Örnek

```cpp
// mulh.cpp
// processor: x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic (__mulh)

int main()
{
    __int64 a = 0x0fffffffffffffffI64;
    __int64 b = 0xf0000000I64;

    __int64 result = __mulh(a, b); // the high 64 bits
    __int64 result2 = a * b; // the low 64 bits

    printf_s(" %#I64x * %#I64x = %#I64x%I64x\n",
             a, b, result, result2);
}
```

```Output
0xfffffffffffffff * 0xf0000000 = 0xeffffffffffffff10000000
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
