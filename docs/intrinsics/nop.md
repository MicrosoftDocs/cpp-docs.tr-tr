---
title: __nop
ms.date: 11/04/2016
f1_keywords:
- __nop
helpviewer_keywords:
- nop instruction
- __nop intrinsic
ms.assetid: 7a2a938b-87e0-476d-a348-03ea7635b6b9
ms.openlocfilehash: 1e76110c1ef0c4b98c295578189eedc99d76eeb9
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59038257"
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
|`__nop`|x86, ARM, x64, ARM64|

**Üst bilgi dosyası** \<intrin.h >

**END Microsoft özgü**

## <a name="remarks"></a>Açıklamalar

`__nop` İşlev, eşdeğer `NOP` makine yönergesi. Belge için x86 ve x64 hakkında daha fazla bilgi için arama "Intel mimarisi yazılım geliştirici el ile 2 birim: Yönerge kümesi başvurusu"konumunda [Intel Corporation'da](https://software.intel.com/articles/intel-sdm) site.

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[__noop](../intrinsics/noop.md)
