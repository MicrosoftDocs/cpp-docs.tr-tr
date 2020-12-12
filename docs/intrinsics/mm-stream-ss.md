---
description: 'Hakkında daha fazla bilgi edinin: _mm_stream_ss'
title: _mm_stream_ss
ms.date: 09/02/2019
f1_keywords:
- _mm_stream_ss
helpviewer_keywords:
- movntss instruction
- _mm_stream_ss intrinsic
ms.assetid: c53dffe9-0dfe-4063-85d3-e8987b870fce
ms.openlocfilehash: 3af79ee38c09f08ab8e1e5300800846c866972a3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97133213"
---
# <a name="_mm_stream_ss"></a>_mm_stream_ss

**Microsoft'a Özgü**

Önbellekleri kirletmeksizin 32 bitlik verileri bir bellek konumuna yazar.

## <a name="syntax"></a>Sözdizimi

```C
void _mm_stream_ss(
   float * Destination,
   __m128 Source
);
```

### <a name="parameters"></a>Parametreler

*Hedefine*\
dışı Kaynak verilerin yazıldığı konuma yönelik bir işaretçi.

*Kaynaktaki*\
'ndaki **`float`** Alt 32 bitine yazılacak değeri içeren 128 bitlik bir sayı.

## <a name="return-value"></a>Döndürülen değer

Yok.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`_mm_stream_ss`|SSE4a|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

İç öğe, `movntss` yönergeyi oluşturur. Bu yönergeyle ilgili donanım desteğini öğrenmek için, `__cpuid` ile iç öğesini çağırın `InfoType=0x80000001` ve bit 6 ' yı denetleyin `CPUInfo[2] (ECX)` . Bu bit, yönerge desteklense 1, aksi durumda 0 ' dır.

Yönergeyi desteklemeyen bir donanım kullanan kodu çalıştırırsanız `_mm_stream_ss` `movntss` , sonuçlar tahmin edilemez olur.

## <a name="example"></a>Örnek

```cpp
// Compile this sample with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

int main()
{
    __m128 vals;
    float f[4];

    f[0] = -1.;
    f[1] = -2.;
    f[2] = -3.;
    f[3] = -4.;
    vals.m128_f32[0] = 0.;
    vals.m128_f32[1] = 1.;
    vals.m128_f32[2] = 2.;
    vals.m128_f32[3] = 3.;
    _mm_stream_ss(&f[3], vals);
    cout << "f[0] = " << f[0] << ", f[1] = " << f[1] << endl;
    cout << "f[1] = " << f[1] << ", f[3] = " << f[3] << endl;
}
```

```Output
f[0] = -1, f[1] = -2
f[2] = -3, f[3] = 3
```

**SON Microsoft 'a özgü**

Bölüm Telif hakkı 2007 Advanced Micro Devices, Inc. Tüm hakları saklıdır. Gelişmiş mikro cihazlar, Inc. izniyle yeniden üretilme.

## <a name="see-also"></a>Ayrıca bkz.

[_mm_stream_sd](../intrinsics/mm-stream-sd.md)\
[_mm_stream_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_stream_ps)\
[_mm_store_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_ss)\
[_mm_sfence](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sfence)\
[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
