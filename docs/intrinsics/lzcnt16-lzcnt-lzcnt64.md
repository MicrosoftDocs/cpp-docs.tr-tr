---
title: __lzcnt16, __lzcnt, __lzcnt64 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __lzcnt64
- __lzcnt16
- __lzcnt
dev_langs:
- C++
helpviewer_keywords:
- __lzcnt intrinsic
- lzcnt instruction
- lzcnt16 intrinsic
- lzcnt intrinsic
- __lzcnt16 intrinsic
- lzcnt64 intrinsic
- __lzcnt64 intrinsic
ms.assetid: 412113e7-052e-46e5-8bfa-d5ad72abc10e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4dd24a6fb51e32e7f1b83b1f238089fc973c0cd7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383161"
---
# <a name="lzcnt16-lzcnt-lzcnt64"></a>__lzcnt16, __lzcnt, __lzcnt64

**Microsoft'a özgü**

Sayıları, bir 16, 32 veya 64-bit tamsayı içinde satır sayısını sıfırlar.

## <a name="syntax"></a>Sözdizimi

```
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

#### <a name="parameters"></a>Parametreler

*value*<br/>
[in] 16, 32 veya 64-bit işaretsiz tamsayı sıfırları için taramak üzere.

## <a name="return-value"></a>Dönüş Değeri

Önde gelen sıfır bit sayısını `value` parametresi. Varsa `value` sıfırsa, boyutu (16, 32 veya 64) giriş işlenenin dönüş değeridir. En önemli biti `value` biri, döndürülen değer sıfırdır.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__lzcnt16`|AMD: Gelişmiş Bit işleme (ABM)<br /><br /> Intel: Haswell|
|`__lzcnt`|AMD: Gelişmiş Bit işleme (ABM)<br /><br /> Intel: Haswell|
|`__lzcnt64`|AMD: Bit işleme (ABM) 64 bit modunda Gelişmiş.<br /><br /> Intel: Haswell|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

Her biri bu iç oluşturur `lzcnt` yönergesi.  Değer boyutu, `lzcnt` yönerge boyutu bağımsız olarak aynı döndürür.  32 bit modunda 64 bit Hayır 64-bit genel amaçlı yazmaç yok, bu nedenle vardır `lzcnt`.

İçin donanım desteği belirlemek için `lzcnt` yönerge çağrı `__cpuid` ile iç `InfoType=0x80000001` ve geçmiş 5 `CPUInfo[2] (ECX)`. Bu bit aksi yönerge destekleniyorsa 1 ve 0 olacaktır. Kullanan kodu bu iç desteği olmayan donanım üzerinde çalıştırdığınız varsa `lzcnt` yönergesi, sonuçların tahmin edilemeyeceğine.

Desteklemeyen bir Intel işlemci üzerinde `lzcnt` yönerge olarak yürütülür yönerge bayt kodlama `bsr` (tarama ters bit). Kod taşınabilirliği önemliyse kullanımını göz önünde bulundurun `_BitScanReverse` iç yerine. Daha fazla bilgi için [_BitScanReverse, _BitScanReverse64](../intrinsics/bitscanreverse-bitscanreverse64.md).

## <a name="example"></a>Örnek

```
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

**END Microsoft özgü**

Bu içerik bölümlerini Micro cihazlar, Inc. Gelişmiş telif hakkı 2007 olan Tüm hakları saklıdır. Gelişmiş Micro cihazlar, Inc. izniyle üretilemez

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)
