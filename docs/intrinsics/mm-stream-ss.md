---
title: _mm_stream_ss
ms.date: 09/02/2019
f1_keywords:
- _mm_stream_ss
helpviewer_keywords:
- movntss instruction
- _mm_stream_ss intrinsic
ms.assetid: c53dffe9-0dfe-4063-85d3-e8987b870fce
ms.openlocfilehash: 005f4f697d64f6ea68b35dc32daf1217be463a2a
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217360"
---
# <a name="_mm_stream_ss"></a>_mm_stream_ss

**Microsoft 'a özgü**

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
'ndaki Alt 32 bitine yazılacak `float` değeri içeren 128 bitlik bir sayı.

## <a name="return-value"></a>Dönüş değeri

Yok.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`_mm_stream_ss`|SSE4a|

**Üst bilgi dosyası** \<Intrin. h >

## <a name="remarks"></a>Açıklamalar

İç öğe, `movntss` yönergeyi oluşturur. Bu yönergeyle ilgili donanım desteğini öğrenmek için, ile `__cpuid` `InfoType=0x80000001` iç öğesini çağırın `CPUInfo[2] (ECX)`ve bit 6 ' yı denetleyin. Bu bit, yönerge desteklense 1, aksi durumda 0 ' dır.

Yönergeyi desteklemeyen bir donanım kullanan `_mm_stream_ss` kodu çalıştırırsanız, sonuçlar tahmin edilemez olur. `movntss`

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
[_mm_sçit](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sfence)\
[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
