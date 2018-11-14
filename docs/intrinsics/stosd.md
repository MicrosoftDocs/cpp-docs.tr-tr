---
title: __stosd
ms.date: 11/04/2016
f1_keywords:
- __stosd
helpviewer_keywords:
- stosd instruction
- rep stosd instruction
- __stosd intrinsic
ms.assetid: 03104247-1cea-49f6-b6f8-287917bf5680
ms.openlocfilehash: c32c439af5544eb561f776381cb1afa98337efcb
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51328844"
---
# <a name="stosd"></a>__stosd

**Microsoft'a özgü**

Bir depolama dize yönergesi oluşturur (`rep stosd`).

## <a name="syntax"></a>Sözdizimi

```
void __stosd(
   unsigned long* Dest,
   unsigned long Data,
   size_t Count
);
```

#### <a name="parameters"></a>Parametreler

*Hedef*<br/>
[out] İşlemin hedefi.

*Veri*<br/>
[in] Depolamak için veriler.

*Sayısı*<br/>
[in] Yazılacak doublewords bloğunu uzunluğu.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__stosd`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

Sonuç doubleword olan `Data` bloğu yazılmış `Count` bellek konumunda doublewords tarafından işaret edilen `Dest`.

Bu yordam yalnızca bir iç öğe olarak kullanılabilir.

## <a name="example"></a>Örnek

```
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

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)