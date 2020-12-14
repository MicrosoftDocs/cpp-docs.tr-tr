---
description: 'Hakkında daha fazla bilgi edinin: __movsb'
title: __movsb
ms.date: 09/02/2019
f1_keywords:
- __movsb
helpviewer_keywords:
- movsb instruction
- rep movsb instruction
- __movsb intrinsic
ms.assetid: ba5469f6-f797-4cd2-bee8-74c7666c26d4
ms.openlocfilehash: 6e4a9ba7482f7f614b80bd0596111874f0087c86
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222456"
---
# <a name="__movsb"></a>__movsb

**Microsoft'a Özgü**

Bir Move String ( `rep movsb` ) yönergesi üretir.

## <a name="syntax"></a>Sözdizimi

```C
void __movsb(
   unsigned char* Destination,
   unsigned const char* Source,
   size_t Count
);
```

### <a name="parameters"></a>Parametreler

*Hedefine*\
dışı Kopyanın hedefine yönelik bir işaretçi.

*Kaynaktaki*\
'ndaki Kopyanın kaynağına yönelik bir işaretçi.

*Biriktirme*\
'ndaki Kopyalanacak bayt sayısı.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__movsb`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

Sonuç `Count` olarak, tarafından işaret edilen ilk bayt `Source` `Destination` dizesine kopyalanır.

Bu yordam yalnızca iç öğe olarak kullanılabilir.

## <a name="example"></a>Örnek

```cpp
// movsb.cpp
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__movsb)

int main()
{
    unsigned char s1[100];
    unsigned char s2[100] = "A big black dog.";
    __movsb(s1, s2, 100);

    printf_s("%s %s", s1, s2);
}
```

```Output
A big black dog. A big black dog.
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
