---
title: _mm_stream_sd
ms.date: 09/02/2019
f1_keywords:
- _mm_stream_sd
helpviewer_keywords:
- _mm_stream_sd intrinsic
- movntsd instruction
ms.assetid: 2b4bea5e-e64e-45fa-9afc-88a2e4b82cfc
ms.openlocfilehash: 7f0c6457cc0806a0f1764300cffa1c9878b8a600
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217366"
---
# <a name="_mm_stream_sd"></a>_mm_stream_sd

**Microsoft 'a özgü**

Önbellekleri kirletmeksizin 64 bitlik verileri bir bellek konumuna yazar.

## <a name="syntax"></a>Sözdizimi

```C
void _mm_stream_sd(
   double * Dest,
   __m128d Source
);
```

### <a name="parameters"></a>Parametreler

*HD*\
dışı Kaynak verilerin yazılacağı konuma yönelik bir işaretçi.

*Kaynaktaki*\
'ndaki Alt 64 bitine yazılacak `double` değeri içeren 128 bitlik bir değer.

## <a name="return-value"></a>Dönüş değeri

Yok.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`_mm_stream_sd`|SSE4a|

**Üst bilgi dosyası** \<Intrin. h >

## <a name="remarks"></a>Açıklamalar

İç öğe, `movntsd` yönergeyi oluşturur. Bu yönergeyle ilgili donanım desteğini öğrenmek için, ile `__cpuid` `InfoType=0x80000001` iç öğesini çağırın `CPUInfo[2] (ECX)`ve bit 6 ' yı denetleyin. Bu bit, donanım bu yönergeyi destekliyorsa 1, aksi takdirde 0 ' dır.

Yönergeyi desteklemeyen bir donanım kullanan `_mm_stream_sd` kodu çalıştırırsanız, sonuçlar tahmin edilemez olur. `movntsd`

## <a name="example"></a>Örnek

```cpp
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

**SON Microsoft 'a özgü**

Bölüm Telif hakkı 2007 Advanced Micro Devices, Inc. Tüm hakları saklıdır. Gelişmiş mikro cihazlar, Inc. izniyle yeniden üretilme.

## <a name="see-also"></a>Ayrıca bkz.

[_mm_stream_ss](../intrinsics/mm-stream-ss.md)\
[_mm_store_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_sd)\
[_mm_sçit](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sfence)\
[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
