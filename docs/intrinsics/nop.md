---
title: __nop
ms.date: 11/04/2016
f1_keywords:
- __nop
helpviewer_keywords:
- nop instruction
- __nop intrinsic
ms.assetid: 7a2a938b-87e0-476d-a348-03ea7635b6b9
ms.openlocfilehash: b0033b0e3a62a16c2856b0e25daeebdb5df0c81f
ms.sourcegitcommit: a1fad0a266b20b313364a74b16c9ac45d089b1e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/11/2019
ms.locfileid: "54220393"
---
# <a name="nop"></a>__nop

**Microsoft'a özgü**

İşlem gerçekleştirmeyecek bir platforma özgü makine koduna oluşturur.

## <a name="syntax"></a>Sözdizimi

```
void __nop();
```

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__nop`|x86, ARM, ARM64 olan x64|

**Üst bilgi dosyası** \<intrin.h >

**END Microsoft özgü**

## <a name="remarks"></a>Açıklamalar

`__nop` İşlev, eşdeğer `NOP` makine yönergesi. Belge için x86 ve x64 hakkında daha fazla bilgi için arama "Intel mimarisi yazılım geliştirici el ile 2 birim: Yönerge kümesi başvurusu"konumunda [Intel Corporation'da](https://software.intel.com/articles/intel-sdm) site.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[__noop](../intrinsics/noop.md)
