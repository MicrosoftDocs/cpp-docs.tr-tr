---
title: __svm_vmrun
ms.date: 09/02/2019
f1_keywords:
- __svm_vmrun
helpviewer_keywords:
- __svm_vmrun intrinsic
- VMRUN instruction
ms.assetid: ae98a781-fc17-47b2-b40f-86fcebf1867b
ms.openlocfilehash: f23df894cc8ad1c270c4c0acbc97cab727e47d93
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219828"
---
# <a name="__svm_vmrun"></a>__svm_vmrun

**Microsoft 'a özgü**

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

`__svm_vmrun` İşlevi, sanal makine konuk kodunu yürütmeye başlamak için VMCB içindeki en az miktarda bilgi kullanır. Karmaşık bir kesmeyi işlemek için daha fazla bilgiye ihtiyacınız varsa veya başka bir konuğa geçiş yapmak için [__svm_vmsave](../intrinsics/svm-vmsave.md) veya [__svm_vmload](../intrinsics/svm-vmload.md) işlevini kullanın.

İşlev, `VMRUN` makine yönergesine eşdeğerdir. `__svm_vmrun` Bu işlev, bir konağın sanal makine izleyicisinin Konuk işletim sistemiyle ve uygulamalarına yönelik etkileşimini destekler. Daha fazla bilgi için "AMD64 mimari programcı 'nin El Ile birim 2 ' yi arayın. Sistem programlama, "belge numarası 24593, düzeltme 3,11 veya üzeri, [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) sitesi.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__svm_vmrun`|x86, x64|

**Üst bilgi dosyası** \<Intrin. h >

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__svm_vmsave](../intrinsics/svm-vmsave.md)\
[__svm_vmload](../intrinsics/svm-vmload.md)
