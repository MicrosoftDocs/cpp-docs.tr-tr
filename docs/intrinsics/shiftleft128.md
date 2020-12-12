---
description: 'Hakkında daha fazla bilgi edinin: __shiftleft128'
title: __shiftleft128
ms.date: 09/02/2019
f1_keywords:
- __shiftleft128
helpviewer_keywords:
- __shiftleft128 intrinsic
ms.assetid: 557b846a-8fb0-469d-91ac-1b1fad80dc2a
ms.openlocfilehash: e0e1402660c2ddb6f5993e5186302ff489ed864f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97306995"
---
# <a name="__shiftleft128"></a>__shiftleft128

**Microsoft'a Özgü**

2 64-bit miktarlar olarak temsil edilen 128 bitlik miktarı `LowPart` ve `HighPart` tarafından belirtilen bir dizi bit ile sola kaydırır `Shift` ve sonucun yüksek 64 bitlerini döndürür.

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

## <a name="return-value"></a>Döndürülen değer

Sonucun yüksek 64 bitleri.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__shiftleft128`|x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

*SHIFT* değeri her zaman modül 64 ' dir; Örneğin, çağırdığınızda, `__shiftleft128(1, 0, 64)` işlev düşük parçalı `0` bitleri sola kayacaktır ve bunun yerine yüksek bir kısmını döndürür, `0` `1` Aksi takdirde beklenmeyebilir.

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

[__shiftright128](../intrinsics/shiftright128.md)\
[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
