---
title: __shiftleft128
ms.date: 09/02/2019
f1_keywords:
- __shiftleft128
helpviewer_keywords:
- __shiftleft128 intrinsic
ms.assetid: 557b846a-8fb0-469d-91ac-1b1fad80dc2a
ms.openlocfilehash: 5da9ac81cedbdd24e10eb438892f88510c32ca24
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218009"
---
# <a name="__shiftleft128"></a>__shiftleft128

**Microsoft 'a özgü**

2 64-bit miktarlar `LowPart` olarak temsil edilen 128 bitlik miktarı ve `HighPart`tarafından `Shift` belirtilen bir dizi bit ile sola kaydırır ve sonucun yüksek 64 bitlerini döndürür.

## <a name="syntax"></a>Sözdizimi

```C
unsigned __int64 __shiftleft128(
   unsigned __int64 LowPart,
   unsigned __int64 HighPart,
   unsigned char Shift
);
```

### <a name="parameters"></a>Parametreler

*LowPart*\
'ndaki SHIFT için 128 bit miktarın düşük 64 biti.

*HighPart*\
'ndaki SHIFT için 128 bit miktarın yüksek 64 biti.

*Karakter*\
'ndaki Kaydırılacak bit sayısı.

## <a name="return-value"></a>Dönüş değeri

Sonucun yüksek 64 bitleri.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__shiftleft128`|X64|

**Üst bilgi dosyası** \<Intrin. h >

## <a name="remarks"></a>Açıklamalar

*SHIFT* değeri her zaman modül 64 ' dir; örneğin `__shiftleft128(1, 0, 64)`, çağırdığınızda, işlev düşük parçalı `0` bitleri sola kayacaktır ve bunun yerine `0` `1` yüksek bir kısmını döndürür, aksi takdirde beklenmeyebilir.

## <a name="example"></a>Örnek

```C
// shiftleft128.c
// processor: IPF, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic (__shiftleft128, __shiftright128)

int main()
{
    unsigned __int64 i = 0x1I64;
    unsigned __int64 j = 0x10I64;
    unsigned __int64 ResultLowPart;
    unsigned __int64 ResultHighPart;

    ResultLowPart = i << 1;
    ResultHighPart = __shiftleft128(i, j, 1);

    // concatenate the low and high parts padded with 0's
    // to display correct hexadecimal 128 bit values
    printf_s("0x%02I64x%016I64x << 1 = 0x%02I64x%016I64x\n",
             j, i, ResultHighPart, ResultLowPart);

    ResultHighPart = j >> 1;
    ResultLowPart = __shiftright128(i, j, 1);

    printf_s("0x%02I64x%016I64x >> 1 = 0x%02I64x%016I64x\n",
             j, i, ResultHighPart, ResultLowPart);
}
```

```Output
0x100000000000000001 << 1 = 0x200000000000000002
0x100000000000000001 >> 1 = 0x080000000000000000
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__kaydırıcı Tri, 128](../intrinsics/shiftright128.md)\
[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
