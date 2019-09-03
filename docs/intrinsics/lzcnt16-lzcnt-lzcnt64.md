---
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
ms.openlocfilehash: fcd801717974a230fbd19cc7802d8f6a011774f7
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221808"
---
# <a name="__lzcnt16-__lzcnt-__lzcnt64"></a>__lzcnt16, __lzcnt, __lzcnt64

**Microsoft 'a özgü**

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

## <a name="return-value"></a>Dönüş değeri

`value` Parametresindeki baştaki sıfır bit sayısı. `value` Sıfırsa, dönüş değeri giriş işleneninin boyutudur (16, 32 veya 64). En önemli bit `value` bir ise, dönüş değeri sıfırdır.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__lzcnt16`|AMD Gelişmiş bit Işleme (ABD)<br /><br /> Intel Haswell|
|`__lzcnt`|AMD Gelişmiş bit Işleme (ABD)<br /><br /> Intel Haswell|
|`__lzcnt64`|AMD 64 bit modunda gelişmiş bit Işleme (ABD).<br /><br /> Intel Haswell|

**Üst bilgi dosyası** \<Intrin. h >

## <a name="remarks"></a>Açıklamalar

Her bir iç yapı, `lzcnt` yönergeyi oluşturur.  `lzcnt` Yönergenin döndürdüğü değerin boyutu bağımsız değişkeninin boyutuyla aynıdır.  32 bit modunda, 64 bit genel amaçlı kayıt yoktur, bu nedenle 64-bit `lzcnt` desteklenmez.

`lzcnt` Yönergeyle ilgili donanım desteğini öğrenmek için, ile `__cpuid` `InfoType=0x80000001` iç öğesini çağırın ve bit 5 `CPUInfo[2] (ECX)`' i denetleyin. Yönerge destekleniyorsa bu bit 1 olur, aksi takdirde 0 olur. `lzcnt` Yönergeyi desteklemeyen bir donanım kullanan kodu çalıştırırsanız, sonuçlar tahmin edilemez olur.

`lzcnt` Yönergesini desteklemeyen Intel işlemcilerde, yönerge bayt kodlaması (bit taraması tersine) olarak `bsr` yürütülür. Kod taşınabilirliği sorun oluşturacaksa, bunun yerine `_BitScanReverse` iç kullanımı göz önünde bulundurun. Daha fazla bilgi için bkz. [_Bitscanreverse, _Bitscansmar64](../intrinsics/bitscanreverse-bitscanreverse64.md).

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
