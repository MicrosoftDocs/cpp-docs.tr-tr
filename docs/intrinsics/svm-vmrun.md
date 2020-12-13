---
description: 'Hakkında daha fazla bilgi edinin: __svm_vmrun'
title: __svm_vmrun
ms.date: 09/02/2019
f1_keywords:
- __svm_vmrun
helpviewer_keywords:
- __svm_vmrun intrinsic
- VMRUN instruction
ms.assetid: ae98a781-fc17-47b2-b40f-86fcebf1867b
ms.openlocfilehash: c01716e496513aa11132fdfc95235a39c7277279
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333706"
---
# <a name="__svm_vmrun"></a>__svm_vmrun

**Microsoft'a Özgü**

Belirtilen sanal makine denetim bloğuna (VMCB) karşılık gelen sanal makine konuk kodunun yürütülmesini başlatır.

## <a name="syntax"></a>Sözdizimi

```C
void __svm_vmrun(
   size_t VmcbPhysicalAddress
);
```

### <a name="parameters"></a>Parametreler

*VmcbPhysicalAddress*\
'ndaki VMCB 'nin fiziksel adresi.

## <a name="remarks"></a>Açıklamalar

`__svm_vmrun`İşlevi, sanal makine konuk kodunu yürütmeye başlamak IÇIN VMCB içindeki en az miktarda bilgi kullanır. Karmaşık bir kesmeyi işlemek için daha fazla bilgiye ihtiyacınız varsa veya başka bir konuğa geçiş yapmak için [__svm_vmsave](../intrinsics/svm-vmsave.md) veya [__svm_vmload](../intrinsics/svm-vmload.md) işlevini kullanın.

`__svm_vmrun`İşlev, `VMRUN` makine yönergesine eşdeğerdir. Bu işlev, bir konağın sanal makine izleyicisinin Konuk işletim sistemiyle ve uygulamalarına yönelik etkileşimini destekler. Daha fazla bilgi için, "AMD64 Architecture Programmer 'ın manuel Volume 2: sistem programlama," belge numarası 24593, düzeltme 3,11 veya sonraki bir sürümü, [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) sitesinde "belgeyi arayın.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__svm_vmrun`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__svm_vmsave](../intrinsics/svm-vmsave.md)\
[__svm_vmload](../intrinsics/svm-vmload.md)
