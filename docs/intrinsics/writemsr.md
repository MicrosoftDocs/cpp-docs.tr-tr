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
ms.openlocfilehash: ac57bac1d132c581ee12048b89d13ed1d1fdb7da
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59026350"
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

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)