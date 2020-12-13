---
description: 'Hakkında daha fazla bilgi edinin: __svm_vmsave'
title: __svm_vmsave
ms.date: 09/02/2019
f1_keywords:
- __svm_vmsave
helpviewer_keywords:
- VMSAVE instruction
- __svm_vmsave intrinsic
ms.assetid: 617a60bd-8514-4ba1-8066-bcf4dd481030
ms.openlocfilehash: 5c0e4eb5f2d4c0f73921572811b070c8f87a2673
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333683"
---
# <a name="__svm_vmsave"></a>__svm_vmsave

**Microsoft'a Özgü**

Belirtilen sanal makine denetim bloğunda (VMCB) işlemci durumunun bir alt kümesini depolar.

## <a name="syntax"></a>Sözdizimi

```C
void __svm_vmsave(
   size_t VmcbPhysicalAddress
);
```

### <a name="parameters"></a>Parametreler

*VmcbPhysicalAddress*\
'ndaki VMCB 'nin fiziksel adresi.

## <a name="remarks"></a>Açıklamalar

`__svm_vmsave`İşlev, `VMSAVE` makine yönergesine eşdeğerdir. Bu işlev, bir konağın sanal makine izleyicisinin Konuk işletim sistemiyle ve uygulamalarına yönelik etkileşimini destekler. Daha fazla bilgi için, "AMD64 Architecture Programmer 'ın manuel Volume 2: sistem programlama," belge numarası 24593, düzeltme 3,11 veya sonraki bir sürümü, [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) sitesinde "belgeyi arayın.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__svm_vmsave`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__svm_vmrun](../intrinsics/svm-vmrun.md)\
[__svm_vmload](../intrinsics/svm-vmload.md)
