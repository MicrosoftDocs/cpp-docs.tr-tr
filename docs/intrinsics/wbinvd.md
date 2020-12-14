---
description: 'Hakkında daha fazla bilgi edinin: __wbinvd'
title: __wbinvd
ms.date: 09/02/2019
f1_keywords:
- __wbinvd
helpviewer_keywords:
- __wbinvd intrinsic
- wbinvd instruction
ms.assetid: 628d0981-39e5-49e1-bd43-706d123af121
ms.openlocfilehash: b40e1b618e49ab317a7b9cdeea647bcd58df7912
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257270"
---
# <a name="__wbinvd"></a>__wbinvd

**Microsoft'a Özgü**

Geri yazma ve ön belleği geçersiz kıl ( `wbinvd` ) yönergesini üretir.

## <a name="syntax"></a>Syntax

```C
void __wbinvd(void);
```

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__wbinvd`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

Bu işlev yalnızca bir ayrıcalık düzeyi (CPL) 0 olan çekirdek modunda kullanılabilir ve yordam yalnızca bir iç öğe olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
