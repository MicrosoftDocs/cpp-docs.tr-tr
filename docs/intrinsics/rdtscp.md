---
title: __rdtscp | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __rdtscp
dev_langs:
- C++
helpviewer_keywords:
- rdtscp intrinsic
- __rdtscp intrinsic
- rdtscp instruction
ms.assetid: f17d9a9c-88bb-44e0-b69d-d516bc1c93ee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 65c4638112d87b0544e9a6c61d839c7ad4664d33
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46415167"
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
|`__rdtscp`|AMD NPT ailesi ten 0Fh veya sonraki sürümler|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

Bu iç oluşturur `rdtscp` yönergesi. Bu yönerge için donanım desteği belirlemek için çağrı `__cpuid` ile iç `InfoType=0x80000001` ve bit 27 `CPUInfo[3] (EDX)`. Bu bit Aksi takdirde yönerge destekleniyorsa 1 ve 0 olur.  Kullanan kodu bu iç desteği olmayan donanım üzerinde çalıştırdığınız varsa `rdtscp` yönergesi, sonuçların tahmin edilemeyeceğine.

> [!CAUTION]
>  Farklı `rdtsc`, `rdtscp` serileştirmek bir yönergesi; Bununla birlikte, derleyici Bu kod taşıyabilirsiniz iç.

Bu nesil donanım TSC değerin yorumu, x64 önceki sürümlerinde farklılık gösterir.  Daha fazla bilgi için donanım kılavuzlarına bakın.

Değer anlamını `TSC_AUX[31:0]` işletim sistemine bağlıdır.

## <a name="example"></a>Örnek

```
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

Telif Hakkı 2007 Gelişmiş Micro cihazlar, Inc. Tüm hakları saklıdır. Gelişmiş Micro cihazlar, Inc. izniyle üretilemez

## <a name="see-also"></a>Ayrıca Bkz.

[__rdtsc](../intrinsics/rdtsc.md)<br/>
[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)