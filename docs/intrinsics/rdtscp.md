---
description: 'Hakkında daha fazla bilgi edinin: __rdtscp'
title: __rdtscp
ms.date: 09/02/2019
f1_keywords:
- __rdtscp
helpviewer_keywords:
- rdtscp intrinsic
- __rdtscp intrinsic
- rdtscp instruction
ms.assetid: f17d9a9c-88bb-44e0-b69d-d516bc1c93ee
ms.openlocfilehash: 511d0f1001c218fd838d4bb315fe8c95f10eb3bf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257503"
---
# <a name="__rdtscp"></a>__rdtscp

**Microsoft'a Özgü**

, `rdtscp` Bellek için yönerge, yazma `TSC_AUX[31:0` ] oluşturur ve 64 bitlik zaman damgası sayacını (sonuç) döndürür `TSC)` .

## <a name="syntax"></a>Sözdizimi

```C
unsigned __int64 __rdtscp(
   unsigned int * AUX
);
```

### <a name="parameters"></a>Parametreler

*AUX*\
dışı Makineye özel kaydın içeriğini içerecek konuma yönelik işaretçi `TSC_AUX[31:0]` .

## <a name="return-value"></a>Döndürülen değer

64 bitlik işaretsiz tamsayı işaret sayısı.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__rdtscp`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

İç öğe, `__rdtscp` `rdtscp` yönergeyi oluşturur. Bu yönergeyle ilgili donanım desteğini öğrenmek için, `__cpuid` iç öğesini çağırın `InfoType=0x80000001` ve bit 27 ' yi denetleyin `CPUInfo[3] (EDX)` . Yönerge destekleniyorsa bu bit 1, değilse 0 ' dır.  Yönergeyi desteklemeyen bir donanım kullanan kodu çalıştırırsanız `rdtscp` , sonuçlar tahmin edilemez olur.

Bu yönerge, tüm önceki yönergelerin yürütülene ve önceki tüm yüklemeler küresel olarak görünür hale gelene kadar bekler. Ancak, bir serileştirme yönergesi değildir. Daha fazla bilgi için bkz. Intel ve AMD el kitapları.

İçindeki değerin anlamı `TSC_AUX[31:0]` işletim sistemine bağlıdır.

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
