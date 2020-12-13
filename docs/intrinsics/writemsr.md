---
description: 'Hakkında daha fazla bilgi edinin: __writemsr'
title: __writemsr
ms.date: 09/02/2019
f1_keywords:
- __writemsr
helpviewer_keywords:
- Write Model Specific Register instruction
- wrmsr instruction
- __writemsr intrinsic
ms.assetid: 938b1553-51a8-4822-a818-6bed79b0fde5
ms.openlocfilehash: 0ab7392d9df07a9083ca095bc7002a6bf7d45628
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331849"
---
# <a name="__writemsr"></a>__writemsr

**Microsoft'a Özgü**

Modele özgü Register () yönergesini yazmayı üretir `wrmsr` .

## <a name="syntax"></a>Sözdizimi

```C
void __writemsr(
   unsigned long Register,
   unsigned __int64 Value
);
```

### <a name="parameters"></a>Parametreler

*Kaydolunamadı*\
'ndaki Modele özgü kayıt.

*Deeri*\
'ndaki Yazılacak değer.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__writemsr`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca çekirdek modunda kullanılabilir ve bu yordam yalnızca iç öğe olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
