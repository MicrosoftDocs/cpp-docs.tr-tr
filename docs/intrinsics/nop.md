---
description: 'Hakkında daha fazla bilgi edinin: __nop'
title: __nop
ms.date: 09/02/2019
f1_keywords:
- __nop
helpviewer_keywords:
- nop instruction
- __nop intrinsic
ms.assetid: 7a2a938b-87e0-476d-a348-03ea7635b6b9
ms.openlocfilehash: 55759e8324511b6ddaa2774bdfdc3554c0032c2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118933"
---
# <a name="__nop"></a>__nop

**Microsoft'a Özgü**

İşlem gerçekleştirmeyen platforma özgü makine kodu oluşturur.

## <a name="syntax"></a>Syntax

```C
void __nop();
```

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__nop`|x86, ARM, x64, ARM64|

**Üst bilgi dosyası**\<intrin.h>

**SON Microsoft 'a özgü**

## <a name="remarks"></a>Açıklamalar

`__nop`İşlev, `NOP` makine yönergesine eşdeğerdir. X86 ve x64 hakkında daha fazla bilgi için, [Intel Corporation](https://software.intel.com/articles/intel-sdm) sitesinde "Intel mimarisi yazılım geliştiricisi el kitabı, toplu 2: yönerge kümesi başvurusu" belgesinde arama yapın.

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__noop](../intrinsics/noop.md)
