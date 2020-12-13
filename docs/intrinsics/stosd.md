---
description: 'Hakkında daha fazla bilgi edinin: __stosd'
title: __stosd
ms.date: 09/02/2019
f1_keywords:
- __stosd
helpviewer_keywords:
- stosd instruction
- rep stosd instruction
- __stosd intrinsic
ms.assetid: 03104247-1cea-49f6-b6f8-287917bf5680
ms.openlocfilehash: 56a29a27790f7f45a9fb3f0ace348759c0b1ff3c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143721"
---
# <a name="__stosd"></a>__stosd

**Microsoft'a Özgü**

Bir depo dizesi yönergesi ( `rep stosd` ) oluşturur.

## <a name="syntax"></a>Sözdizimi

```C
void __stosd(
   unsigned long* Destination,
   unsigned long Data,
   size_t Count
);
```

### <a name="parameters"></a>Parametreler

*Hedefine*\
dışı İşlemin hedefi.

*Verileri*\
'ndaki Depolanacak veriler.

*Biriktirme*\
'ndaki Yazılacak çift sözcük bloğunun uzunluğu.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__stosd`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

Sonuç olarak, doubleword *verilerinin* , *hedefe* göre işaret edilen bellek konumundaki doublewords *sayısı* ile bir blok halinde yazıldığı bir sonucudur.

Bu yordam yalnızca iç öğe olarak kullanılabilir.

## <a name="example"></a>Örnek

```C
// stosd.c
// processor: x86, x64

#include <stdio.h>
#include <memory.h>
#include <intrin.h>

#pragma intrinsic(__stosd)

int main()
{
    unsigned long val = 99999;
    unsigned long a[10];

    memset(a, 0, sizeof(a));
    __stosd(a+1, val, 2);

printf_s( "%u %u %u %u",
              a[0], a[1], a[2], a[3]);
}
```

```Output
0 99999 99999 0
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
