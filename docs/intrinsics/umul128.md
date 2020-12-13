---
description: 'Hakkında daha fazla bilgi edinin: _umul128'
title: _umul128
ms.date: 09/02/2019
f1_keywords:
- __umul128
helpviewer_keywords:
- __umul128 intrinsic
ms.assetid: 13684df3-3ac7-467c-b258-a0e93bc490b5
ms.openlocfilehash: 7fd126b169bd01fc4d51d186879e019f8d86f008
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333599"
---
# <a name="_umul128"></a>_umul128

**Microsoft'a Özgü**

İlk iki bağımsız değişken olarak geçirilen 2 64 bitlik işaretsiz tamsayıları çarpar ve ürünün yüksek 64 bitini tarafından işaret edilen 64-bit işaretsiz tamsayıya koyar `HighProduct` ve ürünün düşük 64 bitlerini döndürür.

## <a name="syntax"></a>Sözdizimi

```C
unsigned __int64 _umul128(
   unsigned __int64 Multiplier,
   unsigned __int64 Multiplicand,
   unsigned __int64 *HighProduct
);
```

### <a name="parameters"></a>Parametreler

*Çarpanını*\
'ndaki Çarpılacak ilk 64 bitlik tamsayı.

*Çoğullıve*\
'ndaki Çarpılacak ikinci 64 bitlik tamsayı.

*HighProduct*\
dışı Ürünün yüksek 64 bitleri.

## <a name="return-value"></a>Döndürülen değer

Ürünün düşük 64 biti.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|Üst bilgi|
|---------------|------------------|------------|
|`_umul128`|x64|\<intrin.h>|

## <a name="example"></a>Örnek

```C
// umul128.c
// processor: x64

#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(_umul128)

int main()
{
    unsigned __int64 a = 0x0fffffffffffffffI64;
    unsigned __int64 b = 0xf0000000I64;
    unsigned __int64 c, d;

    d = _umul128(a, b, &c);

    printf_s("%#I64x * %#I64x = %#I64x%I64x\n", a, b, c, d);
}
```

```Output
0xfffffffffffffff * 0xf0000000 = 0xeffffffffffffff10000000
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
