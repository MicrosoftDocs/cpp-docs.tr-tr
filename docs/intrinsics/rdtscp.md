---
title: __rdtscp
ms.date: 09/02/2019
f1_keywords:
- __rdtscp
helpviewer_keywords:
- rdtscp intrinsic
- __rdtscp intrinsic
- rdtscp instruction
ms.assetid: f17d9a9c-88bb-44e0-b69d-d516bc1c93ee
ms.openlocfilehash: 4dcabd6ed0f7fb3f422927815cbdc91f2b4b9d43
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221315"
---
# <a name="__rdtscp"></a>__rdtscp

**Microsoft 'a özgü**

, Bellek için `TSC_AUX[31:0``TSC)` yönerge, yazma] oluşturur ve 64 bitlik zaman damgası sayacını (sonuç) döndürür. `rdtscp`

## <a name="syntax"></a>Sözdizimi

```C
unsigned __int64 __rdtscp(
   unsigned int * AUX
);
```

### <a name="parameters"></a>Parametreler

*AUX*\
dışı Makineye özel kaydın `TSC_AUX[31:0]`içeriğini içerecek konuma yönelik işaretçi.

## <a name="return-value"></a>Dönüş değeri

64 bitlik işaretsiz tamsayı işaret sayısı.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__rdtscp`|x86, x64|

**Üst bilgi dosyası** \<Intrin. h >

## <a name="remarks"></a>Açıklamalar

İç öğe, `rdtscp` yönergeyi oluşturur. `__rdtscp` Bu yönergeyle ilgili donanım desteğini öğrenmek için, `__cpuid` `InfoType=0x80000001` iç öğesini çağırın `CPUInfo[3] (EDX)`ve bit 27 ' yi denetleyin. Yönerge destekleniyorsa bu bit 1, değilse 0 ' dır.  `rdtscp` Yönergeyi desteklemeyen bir donanım kullanan kodu çalıştırırsanız, sonuçlar tahmin edilemez olur.

Bu yönerge, tüm önceki yönergelerin yürütülene ve önceki tüm yüklemeler küresel olarak görünür hale gelene kadar bekler. Ancak, bir serileştirme yönergesi değildir. Daha fazla bilgi için bkz. Intel ve AMD el kitapları.

İçindeki `TSC_AUX[31:0]` değerin anlamı işletim sistemine bağlıdır.

## <a name="example"></a>Örnek

```cpp
#include <intrin.h>
#include <stdio.h>
int main()
{
    unsigned __int64 i;
    unsigned int ui;
    i = __rdtscp(&ui);
    printf_s("%I64d ticks\n", i);
    printf_s("TSC_AUX was %x\n", ui);
}
```

```Output
3363423610155519 ticks
TSC_AUX was 0
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__rdtsc](../intrinsics/rdtsc.md)\
[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
