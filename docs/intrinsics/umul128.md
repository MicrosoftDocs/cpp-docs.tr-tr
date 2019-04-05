---
title: _umul128
ms.date: 11/04/2016
f1_keywords:
- __umul128
helpviewer_keywords:
- __umul128 intrinsic
ms.assetid: 13684df3-3ac7-467c-b258-a0e93bc490b5
ms.openlocfilehash: afca1e62127ac2dbcfc407982dbe191d379b4acb
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59034971"
---
# <a name="umul128"></a>_umul128

**Microsoft'a Özgü**

İlk iki bağımsız değişken olarak geçirilen iki 64-bit işaretsiz tam sayı ile çarpar ve ürünün yüksek 64 bit işaret ettiği 64-bit işaretsiz tamsayı koyar `HighProduct` ve ürünün düşük 64 bit döndürür.

## <a name="syntax"></a>Sözdizimi

```
unsigned __int64 _umul128(
   unsigned __int64 Multiplier,
   unsigned __int64 Multiplicand,
   unsigned __int64 *HighProduct
);
```

#### <a name="parameters"></a>Parametreler

*Çarpanı*<br/>
[in] Çarpılacak ilk 64-bit tamsayı.

*Çarpan*<br/>
[in] Çarpılacak ikinci 64-bit tamsayı.

*HighProduct*<br/>
[out] Ürünün yüksek 64 bit.

## <a name="return-value"></a>Dönüş Değeri

Ürünün düşük 64 bit.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|Üstbilgi|
|---------------|------------------|------------|
|`_umul128`|X64|\<intrin.h >|

## <a name="example"></a>Örnek

```
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

**END Microsoft'a Özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)
