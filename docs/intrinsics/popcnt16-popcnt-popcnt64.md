---
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
ms.openlocfilehash: 3e5ae7f897500775671f8bd2563028874579a627
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221363"
---
# <a name="__popcnt16-__popcnt-__popcnt64"></a>__popcnt16, __popcnt, __popcnt64

**Microsoft 'a özgü**

Bir 16, 32 `1` -veya 64 bit işaretsiz tamsayının bit sayısını (popülasyon sayısı) sayar.

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

## <a name="return-value"></a>Dönüş değeri

`1` *Değer* parametresindeki bit sayısı.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__popcnt16`|Gelişmiş bit Işleme|
|`__popcnt`|Gelişmiş bit Işleme|
|`__popcnt64`|64 bit modunda gelişmiş bit Işleme.|

**Üst bilgi dosyası** \<Intrin. h >

## <a name="remarks"></a>Açıklamalar

Her bir iç yapı, `popcnt` yönergeyi oluşturur. 32 bit modunda, 64 bit genel amaçlı kayıt yoktur, bu nedenle 64-bit `popcnt` desteklenmez.

`popcnt` Yönergeyle ilgili donanım desteğini öğrenmek için, ile `__cpuid` `InfoType=0x00000001` iç öğesini çağırın ve bit 23 `CPUInfo[2] (ECX)`' ü denetleyin. Yönerge destekleniyorsa bu bit 1, değilse 0 ' dır. Bu iç bilgileri, `popcnt` yönergeyi desteklemeyen donanımda kullanan kodu çalıştırırsanız, sonuçlar tahmin edilemez olur.

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
