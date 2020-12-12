---
description: 'Hakkında daha fazla bilgi edinin: _mm_cvtsi64x_ss'
title: _mm_cvtsi64x_ss
ms.date: 09/02/2019
f1_keywords:
- _mm_cvtsi64x_ss
helpviewer_keywords:
- cvtsi2ss instruction
- _mm_cvtsi64x_ss intrinsic
ms.assetid: 01e5d321-c18a-46fd-a6f6-324364514e1f
ms.openlocfilehash: 81a1af04d4c66cefd9815471baeb3a6095403ddf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167727"
---
# <a name="_mm_cvtsi64x_ss"></a>_mm_cvtsi64x_ss

**Microsoft'a Özgü**

Convert 64 bit tamsayının x64 genişletilmiş sürümünü skaler Single-Precision Floating-Point value ( `cvtsi2ss` ) yönergesine üretir.

## <a name="syntax"></a>Sözdizimi

```C
__m128 _mm_cvtsi64x_ss(
   __m128 a,
   __int64 b
);
```

### <a name="parameters"></a>Parametreler

*a*\
'ndaki **`__m128`** Dört tek duyarlıklı kayan nokta değeri içeren bir yapı.

*kenarı*\
'ndaki Kayan noktalı değere dönüştürülecek 64 bitlik bir tamsayı.

## <a name="return-value"></a>Döndürülen değer

**`__m128`** İlk kayan nokta değeri, dönüştürmenin sonucu olan bir yapı. Diğer üç değer *bir*' dan değiştirilmeden kopyalanır.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`_mm_cvtsi64x_ss`|x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

**`__m128`** Yapı BIR XMM kaydını temsil ettiğinden, iç değer *b* değerinin sistem belleğinden bir XMM kaydına taşınmasına izin verir.

Bu yordam yalnızca iç öğe olarak kullanılabilir.

## <a name="example"></a>Örnek

```cpp
// _mm_cvtsi64x_ss.cpp
// processor: x64

#include <intrin.h>
#include <stdio.h>

#pragma intrinsic(_mm_cvtsi64x_ss)

int main()
{
    __m128 a;
    __int64 b = 54;

    a.m128_f32[0] = 0;
    a.m128_f32[1] = 0;
    a.m128_f32[2] = 0;
    a.m128_f32[3] = 0;
    a = _mm_cvtsi64x_ss(a, b);

    printf_s( "%lf %lf %lf %lf\n",
              a.m128_f32[0], a.m128_f32[1],
              a.m128_f32[2], a.m128_f32[3] );
}
```

```Output
54.000000 0.000000 0.000000 0.000000
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__m128](../cpp/m128.md)\
[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
