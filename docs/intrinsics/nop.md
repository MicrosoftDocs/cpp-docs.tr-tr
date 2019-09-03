---
title: __nop
ms.date: 09/02/2019
f1_keywords:
- __nop
helpviewer_keywords:
- nop instruction
- __nop intrinsic
ms.assetid: 7a2a938b-87e0-476d-a348-03ea7635b6b9
ms.openlocfilehash: 4561bcb84063f3707825c8ca164867d41500e2db
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221665"
---
# <a name="__nop"></a>__nop

**Microsoft 'a özgü**

İşlem gerçekleştirmeyen platforma özgü makine kodu oluşturur.

## <a name="syntax"></a>Sözdizimi

```C
void __nop();
```

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__nop`|x86, ARM, x64, ARM64|

**Üst bilgi dosyası** \<Intrin. h >

**SON Microsoft 'a özgü**

## <a name="remarks"></a>Açıklamalar

İşlev, `NOP` makine yönergesine eşdeğerdir. `__nop` X86 ve x64 hakkında daha fazla bilgi için belgeyi arayın, "Intel mimarisi yazılım geliştiricisi El Ile, Hacim 2: Yönerge kümesi başvurusu, " [Intel Corporation](https://software.intel.com/articles/intel-sdm) sitesinde.

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__noop](../intrinsics/noop.md)
