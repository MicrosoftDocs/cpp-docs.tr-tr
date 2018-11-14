---
title: __stosq
ms.date: 11/04/2016
f1_keywords:
- __stosq
helpviewer_keywords:
- rep stosq instruction
- stosq instruction
- __stosq intrinsic
ms.assetid: 3ea28297-4369-4c2d-bf0c-91fa539ce209
ms.openlocfilehash: f395a8b0fc7194f36bb3388d631628a829f33aca
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51331314"
---
# <a name="stosq"></a>__stosq

**Microsoft'a özgü**

Bir depolama dize yönergesi oluşturur (`rep stosq`).

## <a name="syntax"></a>Sözdizimi

```
void __stosb(
   unsigned __int64* Dest,
   unsigned __int64 Data,
   size_t Count
);
```

#### <a name="parameters"></a>Parametreler

*Hedef*<br/>
[out] İşlemin hedefi.

*Veri*<br/>
[in] Depolamak için veriler.

*Sayısı*<br/>
[in] Yazılacak quadwords bloğunu uzunluğu.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__stosq`|AMD64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

Sonuç quadword olan `Data` bloğu yazılmış `Count` içinde quadwords `Dest` dize.

Bu yordam yalnızca bir iç öğe olarak kullanılabilir.

## <a name="example"></a>Örnek

```
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

## <a name="output"></a>Çıkış

```
0 ffffffffffff ffffffffffff 0
```

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)