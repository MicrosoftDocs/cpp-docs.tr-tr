---
description: 'Hakkında daha fazla bilgi edinin: __svm_vmload'
title: __svm_vmload
ms.date: 09/02/2019
f1_keywords:
- __svm_vmload
helpviewer_keywords:
- __svm_vmload intrinsic
- VMLOAD instruction
ms.assetid: b46a5592-db76-4ffc-8694-2f3494e28bed
ms.openlocfilehash: 975f6aed50007b0b184bbab2b9b48790e5e20616
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333720"
---
# <a name="__svm_vmload"></a>__svm_vmload

**Microsoft'a Özgü**

Belirtilen sanal makine denetim bloğundan (VMCB) işlemci durumunun bir alt kümesini yükler.

## <a name="syntax"></a>Sözdizimi

```C
void __svm_vmload(
   size_t VmcbPhysicalAddress
);
```

### <a name="parameters"></a>Parametreler

*VmcbPhysicalAddress*\
'ndaki VMCB 'nin fiziksel adresi.

## <a name="remarks"></a>Açıklamalar

`__svm_vmload`İşlev, `VMLOAD` makine yönergesine eşdeğerdir. Bu işlev, bir konağın sanal makine izleyicisinin Konuk işletim sistemiyle ve uygulamalarına yönelik etkileşimini destekler. Daha fazla bilgi için, "AMD64 mimari programcı 'nin El Ile Volume 2: sistem programlama," belge numarası 24593, düzeltme 3,11, sonra [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) sitesinde "belgeyi arayın.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__svm_vmload`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__svm_vmrun](../intrinsics/svm-vmrun.md)\
[__svm_vmsave](../intrinsics/svm-vmsave.md)
