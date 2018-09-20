---
title: __nop | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __nop
dev_langs:
- C++
helpviewer_keywords:
- nop instruction
- __nop intrinsic
ms.assetid: 7a2a938b-87e0-476d-a348-03ea7635b6b9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4559549047c9161d27915df856fad4ea461ee633
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46447251"
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
|`__nop`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

**END Microsoft özgü**

## <a name="remarks"></a>Açıklamalar

`__nop` İşlev, eşdeğer `NOP` makine yönergesi. Belge için daha fazla bilgi için arama "Intel mimarisi yazılım geliştirici el ile 2 birim: yönerge kümesi başvurusu" konumunda [Intel Corporation'da](https://software.intel.com/en-us/articles/intel-sdm) site.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[__noop](../intrinsics/noop.md)