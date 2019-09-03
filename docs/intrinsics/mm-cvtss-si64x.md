---
title: _mm_cvtss_si64x
ms.date: 09/02/2019
f1_keywords:
- _mm_cvtss_si64x
helpviewer_keywords:
- cvtss2si intrinsic
- _mm_cvtss_si64x intrinsic
ms.assetid: c279aff2-ee29-4271-8829-3ec691bf7718
ms.openlocfilehash: 6079ed7846a35ff16355f0341d63430f9846057f
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217428"
---
# <a name="_mm_cvtss_si64x"></a>_mm_cvtss_si64x

**Microsoft 'a özgü**

Convert skaler tek duyarlıklı kayan noktalı sayının x64 genişletilmiş sürümünü 64-bit tamsayı (`cvtss2si`) yönergesine üretir.

## <a name="syntax"></a>Sözdizimi

```C
__int64 _mm_cvtss_si64x(
   __m128 value
);
```

### <a name="parameters"></a>Parametreler

*deeri*\
'ndaki Kayan `__m128` nokta değerlerini içeren bir yapı.

## <a name="return-value"></a>Dönüş değeri

64 bitlik bir tamsayı, ilk kayan nokta değerinin bir tamsayıya dönüştürülmesinin sonucu.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`_mm_cvtss_si64x`|X64|

**Üst bilgi dosyası** \<Intrin. h >

## <a name="remarks"></a>Açıklamalar

Yapı değerinin ilk öğesi bir tamsayıya dönüştürülüp döndürülür. MXCSR içindeki yuvarlama Denetim bitleri, yuvarlama davranışını belirlemede kullanılır. Varsayılan yuvarlama modu en yakın değere yuvarlanır ve ondalık bölüm 0,5 ise çift sayıya yuvarlanır. `__m128` Yapı bir XMM kaydını temsil ettiğinden, iç öğe XMM kaydındaki bir değer alır ve bunu sistem belleğine yazar.

Bu yordam yalnızca iç öğe olarak kullanılabilir.

## <a name="example"></a>Örnek

```cpp
// _mm_cvtss_si64x.cpp
// processor: x64
#include <intrin.h>
#include <stdio.h>

#pragma intrinsic(_mm_cvtss_si64x)

int main()
{
    __m128 a;
    __int64 b = 54;

    // _mm_load_ps requires an aligned buffer.
    __declspec(align(16)) float af[4] =
                           { 101.25, 200.75, 300.5, 400.5 };

    // Load a with the floating point values.
    // The values will be copied to the XMM registers.
    a = _mm_load_ps(af);

    // Extract the first element of a and convert to an integer
    b = _mm_cvtss_si64x(a);

    printf_s("%I64d\n", b);
}
```

```Output
101
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__m128d](../cpp/m128d.md)\
[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
