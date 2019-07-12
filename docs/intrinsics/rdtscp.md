---
title: __rdtscp
ms.date: 07/11/2019
f1_keywords:
- __rdtscp
helpviewer_keywords:
- rdtscp intrinsic
- __rdtscp intrinsic
- rdtscp instruction
ms.assetid: f17d9a9c-88bb-44e0-b69d-d516bc1c93ee
ms.openlocfilehash: b8a31c6d19cd171cbe909c75a27c2389866bd578
ms.sourcegitcommit: 0e3da5cea44437c132b5c2ea522bd229ea000a10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2019
ms.locfileid: "67861104"
---
# <a name="rdtscp"></a>__rdtscp

**Microsoft'a özgü**

Oluşturur `rdtscp` yönergesi, Yazar `TSC_AUX[31:0`] bellek ve 64-bit zaman damgası sayacı döndürür (`TSC)` sonucu.

## <a name="syntax"></a>Sözdizimi

```
unsigned __int64 __rdtscp(
   unsigned int * Aux
);
```

#### <a name="parameters"></a>Parametreler

*Yedek*<br/>
[out] İşaretçi makineye özgü kaydının içeriğini içeren bir konuma `TSC_AUX[31:0]`.

## <a name="return-value"></a>Dönüş Değeri

Bir 64-bit işaretsiz tamsayı onay sayısı.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__rdtscp`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

Bu iç oluşturur `rdtscp` yönergesi. Bu yönerge için donanım desteği belirlemek için çağrı `__cpuid` ile iç `InfoType=0x80000001` ve bit 27 `CPUInfo[3] (EDX)`. Bu bit Aksi takdirde yönerge destekleniyorsa 1 ve 0 olur.  Kullanan kodu bu iç desteği olmayan donanım üzerinde çalıştırdığınız varsa `rdtscp` yönergesi, sonuçların tahmin edilemeyeceğine.

Bu yönerge, tüm önceki yönergeleri yürüttünüz ve tüm önceki yüklemelerinin genel olarak görülebilir kadar bekler. Ancak, bu serileştirmek bir yönerge değil. Daha fazla bilgi için Intel ve AMD kılavuzlarına bakın.

Değer anlamını `TSC_AUX[31:0]` işletim sistemine bağlıdır.

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

**END Microsoft özgü**


## <a name="see-also"></a>Ayrıca bkz.

[__rdtsc](../intrinsics/rdtsc.md)<br/>
[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)