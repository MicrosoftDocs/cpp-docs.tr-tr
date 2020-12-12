---
description: 'Hakkında daha fazla bilgi edinin: __lzcnt16, __lzcnt, __lzcnt64'
title: __lzcnt16, __lzcnt, __lzcnt64
ms.date: 09/02/2019
f1_keywords:
- __lzcnt64
- __lzcnt16
- __lzcnt
helpviewer_keywords:
- __lzcnt intrinsic
- lzcnt instruction
- lzcnt16 intrinsic
- lzcnt intrinsic
- __lzcnt16 intrinsic
- lzcnt64 intrinsic
- __lzcnt64 intrinsic
ms.assetid: 412113e7-052e-46e5-8bfa-d5ad72abc10e
ms.openlocfilehash: 75e2c105d05cfe4620f558a4f44c8ae8b9cd6f8f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167740"
---
# <a name="__lzcnt16-__lzcnt-__lzcnt64"></a>__lzcnt16, __lzcnt, __lzcnt64

**Microsoft'a Özgü**

16, 32-veya 64 bit tamsayıların önünde sıfır sayısını sayar.

## <a name="syntax"></a>Sözdizimi

```C
unsigned short __lzcnt16(
   unsigned short value
);
unsigned int __lzcnt(
   unsigned int value
);
unsigned __int64 __lzcnt64(
   unsigned __int64 value
);
```

### <a name="parameters"></a>Parametreler

*deeri*\
'ndaki Baştaki sıfırları taramak için 16, 32-veya 64 bitlik işaretsiz tamsayı.

## <a name="return-value"></a>Döndürülen değer

Parametresindeki baştaki sıfır bit sayısı `value` . `value`Sıfırsa, dönüş değeri giriş işleneninin boyutudur (16, 32 veya 64). En önemli bit `value` bir ise, dönüş değeri sıfırdır.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__lzcnt16`|AMD: Gelişmiş bit Işleme (ABD)<br /><br /> Intel: Haswell|
|`__lzcnt`|AMD: Gelişmiş bit Işleme (ABD)<br /><br /> Intel: Haswell|
|`__lzcnt64`|AMD: 64 bit modunda, gelişmiş bit Işleme (ABD).<br /><br /> Intel: Haswell|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

Her bir iç yapı, `lzcnt` yönergeyi oluşturur.  `lzcnt`Yönergenin döndürdüğü değerin boyutu bağımsız değişkeninin boyutuyla aynıdır.  32 bit modunda, 64 bit genel amaçlı kayıt yoktur, bu nedenle 64-bit `lzcnt` desteklenmez.

Yönergeyle ilgili donanım desteğini öğrenmek için, `lzcnt` `__cpuid` ile iç öğesini çağırın `InfoType=0x80000001` ve bit 5 ' i denetleyin `CPUInfo[2] (ECX)` . Yönerge destekleniyorsa bu bit 1 olur, aksi takdirde 0 olur. Yönergeyi desteklemeyen bir donanım kullanan kodu çalıştırırsanız `lzcnt` , sonuçlar tahmin edilemez olur.

Yönergesini desteklemeyen Intel işlemcilerde `lzcnt` , yönerge bayt kodlaması `bsr` (bit taraması tersine) olarak yürütülür. Kod taşınabilirliği sorun oluşturacaksa, bunun yerine iç kullanımı göz önünde bulundurun `_BitScanReverse` . Daha fazla bilgi için bkz. [_BitScanReverse, _BitScanReverse64](../intrinsics/bitscanreverse-bitscanreverse64.md).

## <a name="example"></a>Örnek

```cpp
// Compile this test with: /EHsc
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
    usr = __lzcnt16(us[i]);
    cout << "__lzcnt16(0x" << hex << us[i] << ") = " << dec << usr << endl;
  }

  for (int i=0; i<4; i++) {
    uir = __lzcnt(ui[i]);
    cout << "__lzcnt(0x" << hex << ui[i] << ") = " << dec << uir << endl;
  }
}
```

```Output
__lzcnt16(0x0) = 16
__lzcnt16(0xff) = 8
__lzcnt16(0xffff) = 0
__lzcnt(0x0) = 32
__lzcnt(0xff) = 24
__lzcnt(0xffff) = 16
__lzcnt(0xffffffff) = 0
```

**SON Microsoft 'a özgü**

Bu içeriğin kısımları Advanced Micro Devices, Inc tarafından telif hakkı 2007 ' dir. Tüm hakları saklıdır. Gelişmiş mikro cihazlar, Inc. izniyle yeniden üretilme.

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
