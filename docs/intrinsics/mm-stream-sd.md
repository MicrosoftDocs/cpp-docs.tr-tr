---
title: _mm_stream_sd
ms.date: 11/04/2016
f1_keywords:
- _mm_stream_sd
helpviewer_keywords:
- _mm_stream_sd intrinsic
- movntsd instruction
ms.assetid: 2b4bea5e-e64e-45fa-9afc-88a2e4b82cfc
ms.openlocfilehash: cf57d485ab3dd268d217b2ef44ff53bcec3d2e63
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51518144"
---
# <a name="mmstreamsd"></a>_mm_stream_sd

**Microsoft'a özgü**

64-bit veri önbelleklerinin kirletmesini olmadan bir bellek konumuna yazar.

## <a name="syntax"></a>Sözdizimi

```
void _mm_stream_sd(
   double * Dest,
   __m128d Source
);
```

#### <a name="parameters"></a>Parametreler

*Hedef*<br/>
[out] Kaynak verilerin yazılacağı konum için bir işaretçi.

*Kaynak*<br/>
[in] 128-bit değeri içeren bir `double` 64 bit kendi alt yazılacak değer...

## <a name="return-value"></a>Dönüş Değeri

Yok.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`_mm_stream_sd`|SSE4a|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

Bu iç oluşturur `movntsd` yönergesi. Bu yönerge için donanım desteği belirlemek için çağrı `__cpuid` ile iç `InfoType=0x80000001` ve 6 bit `CPUInfo[2] (ECX)`. Aksi takdirde bu yönerge ve 0 donanım destekliyorsa, bu bit 1'dir.

Kullanan kodu çalıştırırsanız `_mm_stream_sd` desteği olmayan donanımda iç `movntsd` yönergesi, sonuçların tahmin edilemeyeceğine.

## <a name="example"></a>Örnek

```
// Compile this sample with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

int main()
{
    __m128d vals;
    double d[2];

    d[0] = -1.;
    d[1] = -2.;
    vals.m128d_f64[0] = 0.;
    vals.m128d_f64[1] = 1.;
    _mm_stream_sd(&d[1], vals);
    cout << "d[0] = " << d[0] << ", d[1] = " << d[1] << endl;
}
```

```Output
d[0] = -1, d[1] = 1
```

**END Microsoft özgü**

Telif Hakkı 2007 Gelişmiş Micro cihazlar, Inc. Tüm hakları saklıdır. Gelişmiş Micro cihazlar, Inc. izniyle üretilemez

## <a name="see-also"></a>Ayrıca Bkz.

[_mm_stream_ss](../intrinsics/mm-stream-ss.md)<br/>
[_mm_store_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_sd)<br/>
[_mm_sfence](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sfence)<br/>
[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)