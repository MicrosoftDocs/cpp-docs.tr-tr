---
title: _mm_stream_ss
ms.date: 11/04/2016
f1_keywords:
- _mm_stream_ss
helpviewer_keywords:
- movntss instruction
- _mm_stream_ss intrinsic
ms.assetid: c53dffe9-0dfe-4063-85d3-e8987b870fce
ms.openlocfilehash: 089f8d5501c18b679a3d5878bb30762d2dcc1e04
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438915"
---
# <a name="mmstreamss"></a>_mm_stream_ss

**Microsoft'a özgü**

32-bit veri önbelleklerinin kirletmesini olmadan bir bellek konumuna yazar.

## <a name="syntax"></a>Sözdizimi

```
void _mm_stream_ss(
   float * Dest,
   __m128 Source
);
```

#### <a name="parameters"></a>Parametreler

*Hedef*<br/>
[out] Kaynak veri yazıldığı konumu için bir işaretçi.

*Kaynak*<br/>
[in] İçeren 128 bit bir sayı `float` 32 bit kendi alt yazılacak değer...

## <a name="return-value"></a>Dönüş Değeri

Yok.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`_mm_stream_ss`|SSE4a|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

Bu iç oluşturur `movntss` yönergesi. Bu yönerge için donanım desteği belirlemek için çağrı `__cpuid` ile iç `InfoType=0x80000001` ve 6 bit `CPUInfo[2] (ECX)`. Bu bit Aksi takdirde yönerge desteklendiğinde 1 ve 0 olur.

Kullanan kodu çalıştırırsanız `_mm_stream_ss` desteği olmayan donanımda iç `movntss` yönergesi, sonuçların tahmin edilemeyeceğine.

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

**END Microsoft özgü**

Telif Hakkı 2007 Gelişmiş Micro cihazlar, Inc. Tüm hakları saklıdır. Gelişmiş Micro cihazlar, Inc. izniyle üretilemez

## <a name="see-also"></a>Ayrıca Bkz.

[_mm_stream_sd](../intrinsics/mm-stream-sd.md)<br/>
[_mm_stream_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_stream_ps)<br/>
[_mm_store_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_ss)<br/>
[_mm_sfence](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sfence)<br/>
[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)