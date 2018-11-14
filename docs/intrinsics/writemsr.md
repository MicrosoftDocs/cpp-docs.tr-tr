---
title: __writemsr
ms.date: 11/04/2016
f1_keywords:
- __writemsr
helpviewer_keywords:
- Write Model Specific Register instruction
- wrmsr instruction
- __writemsr intrinsic
ms.assetid: 938b1553-51a8-4822-a818-6bed79b0fde5
ms.openlocfilehash: f4af272ccafec9789497d0321c0769c2906f76b7
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51330300"
---
# <a name="writemsr"></a>__writemsr

**Microsoft'a özgü**

Yazma modeli belirli kaydetmeyi oluşturur (`wrmsr`) yönerge.

## <a name="syntax"></a>Sözdizimi

```
void __writemsr(
   unsigned long Register,
   unsigned __int64 Value
);
```

#### <a name="parameters"></a>Parametreler

*Kaydolun*<br/>
[in] Model belirli kaydolun.

*Değer*<br/>
[in] Yazılacak değer.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__writemsr`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

Bu yordam yalnızca bir iç öğe olarak kullanılabilir ve bu işlevi yalnızca çekirdek modunda kullanılır.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)