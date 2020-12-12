---
description: 'Hakkında daha fazla bilgi edinin: __popcnt16, __popcnt, __popcnt64'
title: __popcnt16, __popcnt, __popcnt64
ms.date: 09/02/2019
f1_keywords:
- __popcnt64
- __popcnt
- __popcnt16
helpviewer_keywords:
- popcnt instruction
- __popcnt16
- __popcnt64
- __popcnt
ms.assetid: e525b236-adc8-42df-9b9b-8b7d8c245d3b
ms.openlocfilehash: cb95ff09d589cfd9a9cfc438d0334cf68f073825
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257530"
---
# <a name="__popcnt16-__popcnt-__popcnt64"></a>__popcnt16, __popcnt, __popcnt64

**Microsoft'a Özgü**

`1`Bir 16, 32-veya 64 bit işaretsiz tamsayının bit sayısını (popülasyon sayısı) sayar.

## <a name="syntax"></a>Sözdizimi

```C
unsigned short __popcnt16(
   unsigned short value
);
unsigned int __popcnt(
   unsigned int value
);
unsigned __int64 __popcnt64(
   unsigned __int64 value
);
```

### <a name="parameters"></a>Parametreler

*deeri*\
'ndaki Popülasyon sayısını istediğimiz için 16, 32-veya 64 bitlik işaretsiz tamsayı.

## <a name="return-value"></a>Döndürülen değer

`1` *Değer* parametresindeki bit sayısı.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__popcnt16`|Gelişmiş bit Işleme|
|`__popcnt`|Gelişmiş bit Işleme|
|`__popcnt64`|64 bit modunda gelişmiş bit Işleme.|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

Her bir iç yapı, `popcnt` yönergeyi oluşturur. 32 bit modunda, 64 bit genel amaçlı kayıt yoktur, bu nedenle 64-bit `popcnt` desteklenmez.

Yönergeyle ilgili donanım desteğini öğrenmek için, `popcnt` `__cpuid` ile iç öğesini çağırın `InfoType=0x00000001` ve bit 23 ' ü denetleyin `CPUInfo[2] (ECX)` . Yönerge destekleniyorsa bu bit 1, değilse 0 ' dır. Bu iç bilgileri, yönergeyi desteklemeyen donanımda kullanan kodu çalıştırırsanız `popcnt` , sonuçlar tahmin edilemez olur.

## <a name="example"></a>Örnek

```cpp
#include <iostream>
#include <intrin.h>
using namespace std;

int main()
{
  unsigned short us[3] = {0, 0xFF, 0xFFFF};
  unsigned short usr;
  unsigned int   ui[4] = {0, 0xFF, 0xFFFF, 0xFFFFFFFF};
  unsigned int   uir;

  for (int i=0; i<3; i++) {
    usr = __popcnt16(us[i]);
    cout << "__popcnt16(0x" << hex << us[i] << ") = " << dec << usr << endl;
  }

  for (int i=0; i<4; i++) {
    uir = __popcnt(ui[i]);
    cout << "__popcnt(0x" << hex << ui[i] << ") = " << dec << uir << endl;
  }
}
```

```Output
__popcnt16(0x0) = 0
__popcnt16(0xff) = 8
__popcnt16(0xffff) = 16
__popcnt(0x0) = 0
__popcnt(0xff) = 8
__popcnt(0xffff) = 16
__popcnt(0xffffffff) = 32
```

**SON Microsoft 'a özgü**

Bölüm Telif hakkı 2007 Advanced Micro Devices, Inc. Tüm hakları saklıdır. Gelişmiş mikro cihazlar, Inc. izniyle yeniden üretilme.

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
