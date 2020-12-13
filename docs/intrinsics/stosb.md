---
description: 'Hakkında daha fazla bilgi edinin: __stosb'
title: __stosb
ms.date: 09/02/2019
f1_keywords:
- __stosb
helpviewer_keywords:
- rep stosb instruction
- __stosb intrinsic
- stosb instruction
ms.assetid: 634589ed-2da3-439b-a381-a214d89bf10c
ms.openlocfilehash: 8fa8b506b1b4a15738d2eaebeeaad4b547b2f02e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143734"
---
# <a name="__stosb"></a>__stosb

**Microsoft'a Özgü**

Bir depo dizesi yönergesi ( `rep stosb` ) oluşturur.

## <a name="syntax"></a>Sözdizimi

```C
void __stosb(
   unsigned char* Destination,
   unsigned char Data,
   size_t Count
);
```

### <a name="parameters"></a>Parametreler

*Hedefine*\
dışı İşlemin hedefi.

*Verileri*\
'ndaki Depolanacak veriler.

*Biriktirme*\
'ndaki Yazılacak bayt bloğunun uzunluğu.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__stosb`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

Sonuç, karakter *verilerinin* , *hedef* dizedeki bir *Count* bytes bloğuna yazıldığı bir sonucudur.

Bu yordam yalnızca iç öğe olarak kullanılabilir.

## <a name="example"></a>Örnek

```C
// stosb.c
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__stosb)

int main()
{
    unsigned char c = 0x40; /* '@' character */
    unsigned char s[] = "*********************************";

    printf_s("%s\n", s);
    __stosb((unsigned char*)s+1, c, 6);
    printf_s("%s\n", s);

}
```

```Output
*********************************
*@@@@@@**************************
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
