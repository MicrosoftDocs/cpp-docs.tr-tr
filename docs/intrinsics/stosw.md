---
description: 'Hakkında daha fazla bilgi edinin: __stosw'
title: __stosw
ms.date: 09/02/2019
f1_keywords:
- __stosw
helpviewer_keywords:
- stosw instruction
- __stosw intrinsic
- rep stosw instruction
ms.assetid: 7620fd1d-dba5-40e3-8e07-01aa68895133
ms.openlocfilehash: 2995276fb255858d6c3dd9f438487726e75fdf1e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143695"
---
# <a name="__stosw"></a>__stosw

**Microsoft'a Özgü**

Bir depo dizesi yönergesi ( `rep stosw` ) oluşturur.

## <a name="syntax"></a>Sözdizimi

```C
void __stosw(
   unsigned short* Destination,
   unsigned short Data,
   size_t Count
);
```

### <a name="parameters"></a>Parametreler

*Hedefine*\
dışı İşlemin hedefi.

*Verileri*\
'ndaki Depolanacak veriler.

*Biriktirme*\
'ndaki Yazılacak sözcüklerin bloğunun uzunluğu.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__stosw`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

Sonuç olarak, Word *verilerinin* *hedef* dizedeki bir *sayı* kelime bloğu içine yazılır.

Bu yordam yalnızca iç öğe olarak kullanılabilir.

## <a name="example"></a>Örnek

```C
// stosw.c
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__stosw)

int main()
{
    unsigned short val = 128;
    unsigned short a[100];
    memset(a, 0, sizeof(a));
    __stosw(a+10, val, 2);
    printf_s("%u %u %u %u", a[9], a[10], a[11], a[12]);
}
```

```Output
0 128 128 0
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
