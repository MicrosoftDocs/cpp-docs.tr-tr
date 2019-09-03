---
title: __svm_vmsave
ms.date: 09/02/2019
f1_keywords:
- __svm_vmsave
helpviewer_keywords:
- VMSAVE instruction
- __svm_vmsave intrinsic
ms.assetid: 617a60bd-8514-4ba1-8066-bcf4dd481030
ms.openlocfilehash: f91efa7116a8a8e9ebe27c7e5e4e64c4f1533e9d
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219787"
---
# <a name="__svm_vmsave"></a>__svm_vmsave

**Microsoft 'a özgü**

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

İşlev, `VMSAVE` makine yönergesine eşdeğerdir. `__svm_vmsave` Bu işlev, bir konağın sanal makine izleyicisinin Konuk işletim sistemiyle ve uygulamalarına yönelik etkileşimini destekler. Daha fazla bilgi için "AMD64 mimari programcı 'nin El Ile birim 2 ' yi arayın. Sistem programlama, "belge numarası 24593, düzeltme 3,11 veya üzeri, [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) sitesi.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__svm_vmsave`|x86, x64|

**Üst bilgi dosyası** \<Intrin. h >

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__svm_vmrun](../intrinsics/svm-vmrun.md)\
[__svm_vmload](../intrinsics/svm-vmload.md)
