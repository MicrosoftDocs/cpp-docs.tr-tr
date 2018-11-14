---
title: __movsd
ms.date: 11/04/2016
f1_keywords:
- __movsd
helpviewer_keywords:
- rep movsd instruction
- __movsd intrinsic
- movsd instruction
ms.assetid: eb5cccf3-aa76-47f0-b9fc-eeca38fd943f
ms.openlocfilehash: 89c2e7bf6045821d01b23608552776aaf389b0cf
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51331015"
---
# <a name="movsd"></a>__movsd

**Microsoft'a özgü**

Taşıma bir dize oluşturur (`rep movsd`) yönerge.

## <a name="syntax"></a>Sözdizimi

```
void __movsd(
   unsigned long* Dest,
   unsigned long* Source,
   size_t Count
);
```

#### <a name="parameters"></a>Parametreler

*Hedef*<br/>
[out] İşlemin hedefi.

*Kaynak*<br/>
[in] İşlem kaynağı.

*Sayısı*<br/>
[in] Kopyalanacak doublewords sayısı.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__movsd`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

Sonuç ilk `Count` doublewords tarafından işaret edilen `Source` kopyalanır `Dest` dize.

Bu yordam yalnızca bir iç öğe olarak kullanılabilir.

## <a name="example"></a>Örnek

```
// movsd.cpp
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__movsd)

int main()
{
    unsigned long a1[10];
    unsigned long a2[10] = {950, 850, 750, 650, 550, 450, 350,
                            250, 150, 50};
    __movsd(a1, a2, 10);

    for (int i = 0; i < 10; i++)
        printf_s("%d ", a1[i]);
    printf_s("\n");
}
```

```Output
950 850 750 650 550 450 350 250 150 50
```

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)