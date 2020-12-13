---
description: 'Hakkında daha fazla bilgi edinin: __stosq'
title: __stosq
ms.date: 09/02/2019
f1_keywords:
- __stosq
helpviewer_keywords:
- rep stosq instruction
- stosq instruction
- __stosq intrinsic
ms.assetid: 3ea28297-4369-4c2d-bf0c-91fa539ce209
ms.openlocfilehash: 5fce587c163da18679750c20ec697c489ecf5d90
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143708"
---
# <a name="__stosq"></a>__stosq

**Microsoft'a Özgü**

Bir depo dizesi yönergesi ( `rep stosq` ) oluşturur.

## <a name="syntax"></a>Sözdizimi

```C
void __stosb(
   unsigned __int64* Destination,
   unsigned __int64 Data,
   size_t Count
);
```

### <a name="parameters"></a>Parametreler

*Hedefine*\
dışı İşlemin hedefi.

*Verileri*\
'ndaki Depolanacak veriler.

*Biriktirme*\
'ndaki Yazılacak quadwords bloğunun uzunluğu.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__stosq`|'TÜR|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

Sonuç olarak, quadword *verilerinin* , *hedef* dizede quadwords *sayısı* bir blok içine yazılır.

Bu yordam yalnızca iç öğe olarak kullanılabilir.

## <a name="example"></a>Örnek

```C
// stosq.c
// processor: x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__stosq)

int main()
{
   unsigned __int64 val = 0xFFFFFFFFFFFFI64;
   unsigned __int64 a[10];
   memset(a, 0, sizeof(a));
   __stosq(a+1, val, 2);
   printf("%I64x %I64x %I64x %I64x", a[0], a[1], a[2], a[3]);
}
```

```Output
0 ffffffffffff ffffffffffff 0
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
