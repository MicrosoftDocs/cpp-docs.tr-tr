---
title: _umul128
ms.date: 09/02/2019
f1_keywords:
- __umul128
helpviewer_keywords:
- __umul128 intrinsic
ms.assetid: 13684df3-3ac7-467c-b258-a0e93bc490b5
ms.openlocfilehash: 205f0f7f9046ede624bb09e18d8ede32fadbc3de
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219699"
---
# <a name="_umul128"></a>_umul128

**Microsoft 'a özgü**

İlk iki bağımsız değişken olarak geçirilen 2 64 bitlik işaretsiz tamsayıları çarpar ve ürünün yüksek 64 bitini tarafından `HighProduct` işaret edilen 64-bit işaretsiz tamsayıya koyar ve ürünün düşük 64 bitlerini döndürür.

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

## <a name="return-value"></a>Dönüş değeri

Ürünün düşük 64 biti.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|Üstbilgi|
|---------------|------------------|------------|
|`_umul128`|X64|\<Intrin. h >|

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
