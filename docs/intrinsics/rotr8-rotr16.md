---
description: 'Hakkında daha fazla bilgi edinin: _rotr8 _rotr16'
title: _rotr8, _rotr16
ms.date: 09/02/2019
f1_keywords:
- _rotr16
- _rotr8
helpviewer_keywords:
- _rotr8 intrinsic
- _rotr16 intrinsic
ms.assetid: dfbd2c82-82b4-427a-ad52-51609027ebff
ms.openlocfilehash: 95908956fe34b654c3602f27b495eb58a0b8f8c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307047"
---
# <a name="_rotr8-_rotr16"></a>_rotr8, _rotr16

**Microsoft'a Özgü**

Giriş değerlerini, belirtilen sayıda bit konumuyla en az önemli bit (LSB) sağa döndürün.

## <a name="syntax"></a>Sözdizimi

```C
unsigned char _rotr8(
   unsigned char value,
   unsigned char shift
);
unsigned short _rotr16(
   unsigned short value,
   unsigned char shift
);
```

### <a name="parameters"></a>Parametreler

*deeri*\
'ndaki Döndürülecek değer.

*karakter*\
'ndaki Döndürülecek bit sayısı.

## <a name="return-value"></a>Döndürülen değer

Döndürülen değer.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`_rotr8`|x86, ARM, x64, ARM64|
|`_rotr16`|x86, ARM, x64, ARM64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

Sağ kaydırma işleminin aksine, doğru bir döndürme yürütürken, düşük uca düşen düşük sıralı bitler yüksek sıralı bit konumlarına taşınır.

## <a name="example"></a>Örnek

```cpp
// rotr.cpp
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(_rotr8, _rotr16)

int main()
{
    unsigned char c = 'A', c1, c2;

    for (int i = 0; i < 8; i++)
    {
       printf_s("Rotating 0x%x right by %d bits gives 0x%x\n", c,
                i, _rotr8(c, i));
    }

    unsigned short s = 0x12;
    int nBit = 10;

    printf_s("Rotating unsigned short 0x%x right by %d bits "
             "gives 0x%x\n",
            s, nBit, _rotr16(s, nBit));
}
```

```Output
Rotating 0x41 right by 0 bits gives 0x41
Rotating 0x41 right by 1 bits gives 0xa0
Rotating 0x41 right by 2 bits gives 0x50
Rotating 0x41 right by 3 bits gives 0x28
Rotating 0x41 right by 4 bits gives 0x14
Rotating 0x41 right by 5 bits gives 0xa
Rotating 0x41 right by 6 bits gives 0x5
Rotating 0x41 right by 7 bits gives 0x82
Rotating unsigned short 0x12 right by 10 bits gives 0x480
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_rotl8, _rotl16](../intrinsics/rotl8-rotl16.md)\
[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
