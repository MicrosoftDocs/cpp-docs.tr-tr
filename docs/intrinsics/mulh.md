---
title: __mulh
ms.date: 11/04/2016
f1_keywords:
- __mulh
helpviewer_keywords:
- __mulh intrinsic
ms.assetid: cd2ab093-9ef6-404d-ac34-0bee033882f3
ms.openlocfilehash: 28826f285d23b083883237ff1fb02684e32d278c
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326127"
---
# <a name="mulh"></a>__mulh

**Microsoft'a özgü**

Yüksek 64 bit ürünün iki 64-bit imzalı tamsayı döndürür.

## <a name="syntax"></a>Sözdizimi

```
__int64 __mulh(
   __int64 a,
   __int64 b
);
```

#### <a name="parameters"></a>Parametreler

*a*<br/>
[in] Çarpılacak ilk sayı.

*b*<br/>
[in] Çarpılacak ikinci sayı.

## <a name="return-value"></a>Dönüş Değeri

Çarpma 128-bit sonucunu yüksek 64 bit.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__mulh`|X64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

Bu yordam yalnızca bir iç öğe olarak kullanılabilir.

## <a name="example"></a>Örnek

```
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

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)