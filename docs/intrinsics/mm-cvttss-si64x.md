---
description: 'Hakkında daha fazla bilgi edinin: _mm_cvttss_si64x'
title: _mm_cvttss_si64x
ms.date: 09/02/2019
f1_keywords:
- _mm_cvttss_si64x
helpviewer_keywords:
- _mm_cvttss_si64x intrinsic
- cvttss2si instruction
ms.assetid: f9a3fd07-5bd8-4758-8744-6315c082cf87
ms.openlocfilehash: a4af7b726d0f15099586bc94348ab4ba7ebf5b8e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167636"
---
# <a name="_mm_cvttss_si64x"></a>_mm_cvttss_si64x

**Microsoft'a Özgü**

Dönüştürme işleminin x64 genişletilmiş sürümünü kesme Single-Precision Floating-Point numarası 64-bit tamsayı ( `cvttss2si` ) yönergesiyle yayar.

## <a name="syntax"></a>Sözdizimi

```C
__int64 _mm_cvttss_si64x(
   __m128 value
);
```

### <a name="parameters"></a>Parametreler

*deeri*\
'ndaki **`__m128`** Tek duyarlıklı kayan nokta değerleri içeren bir yapı.

## <a name="return-value"></a>Döndürülen değer

İlk kayan nokta değerinin 64 bitlik bir tamsayıya dönüştürülmesinin sonucu.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`_mm_cvttss_si64x`|x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

İç öğe `_mm_cvtss_si64x` yalnızca bu geçersiz dönüştürmelerde sıfıra doğru kesilir. **`__m128`** Yapı BIR XMM kaydını temsil ettiğinden, oluşturulan yönerge verileri BIR XMM kaydındaki sistem belleğine taşıdır.

Bu yordam yalnızca iç öğe olarak kullanılabilir.

## <a name="example"></a>Örnek

```cpp
// _mm_cvttss_si64x.cpp
// processor: x64
#include <intrin.h>
#include <stdio.h>

#pragma intrinsic(_mm_cvttss_si64x)

int main()
{
    __m128 a;
    __int64 b = 54;

    // _mm_load_ps requires an aligned buffer.
    __declspec(align(16)) float af[4] = { 101.5, 200.75,
                                          300.5, 400.5 };

    // Load a with the floating point values.
    // The values will be copied to the XMM registers.
    a = _mm_load_ps(af);

    // Extract the first element of a and convert to an integer
    b = _mm_cvttss_si64x(a);

    printf_s("%I64d\n", b);
}
```

```Output
101
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__m128](../cpp/m128.md)\
[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
